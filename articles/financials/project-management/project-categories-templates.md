---
title: "Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation"
description: "Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: c4d09fde2cf4335553243c136590f9f3135db97a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="97f5f-103">Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="97f5f-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="97f5f-104">Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="97f5f-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> - <span data-ttu-id="97f5f-105">Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.0.</span><span class="sxs-lookup"><span data-stu-id="97f5f-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in Microsoft Dynamics 365 for Finance and Operations version 8.0.</span></span>
> - <span data-ttu-id="97f5f-106">Funkcja integrowania wartości rzeczywistych jest dostępna w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.01 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="97f5f-106">Actuals integration is available in Microsoft Dynamics 365 for Finance and Operations version 8.0.1 or later.</span></span>
> - <span data-ttu-id="97f5f-107">Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition 7.3.0, po zainstalowaniu aktualizacji KB 4132657 i 4132660 możesz używać szablonów, aby integrować zadania projektu, kategorie transakcji wydatkowych, szacunki godzin, szacunki wydatków i wartości rzeczywiste oraz konfigurować blokowanie funkcji.</span><span class="sxs-lookup"><span data-stu-id="97f5f-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="97f5f-108">Jeśli należy zresetować zasady podziału księgowań, zalecamy dodatkowo zainstalować aktualizację KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="97f5f-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="97f5f-109">Przepływ danych między programami Project Service Automation i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="97f5f-109">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="97f5f-110">Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-110">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="97f5f-111">Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących kategorii transakcji wydatkowych w projektach pomiędzy rozwiązaniem Project Service Automation i rozwiązaniem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-111">The integration templates that are available with the Data integration feature enable the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="97f5f-112">Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Finance and Operations, przepływ integracji następuje najpierw z programu Finance and Operations do programu Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="97f5f-112">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation.</span></span> <span data-ttu-id="97f5f-113">Identyfikatory integracji kategorii wydatków w projekcie są następnie aktualizowane poprzez synchronizację z programu Project Service Automation do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-113">The integration IDs of the project expense categories are then updated through synchronization from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="97f5f-114">Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Project Service Automation, przepływ integracji następuje najpierw z programu Project Service Automation do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-114">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="97f5f-115">Kategorie projektu muszą być skonfigurowane w rozwiązaniu Finance and Operations przed synchronizacją z rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="97f5f-115">The project categories must already be configured in Finance and Operations before the synchronization from Project Service Automation.</span></span> <span data-ttu-id="97f5f-116">Następnie przeprowadź synchronizację z rozwiązania Finance and Operations ponownie do rozwiązania Project Service Automation, a następnie jeszcze raz z rozwiązania Project Service Automation do rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-116">Then synchronize from Finance and Operations back to Project Service Automation, and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="97f5f-117">W ten sposób zapewniasz, że kategorie są połączone i nie powstają żadne duplikaty.</span><span class="sxs-lookup"><span data-stu-id="97f5f-117">In this way, you help guarantee that the categories are linked, and that no duplicates are created.</span></span>

> [!NOTE]
> <span data-ttu-id="97f5f-118">Na ogół kategorie wydatków projektu są zarządzane w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-118">Typically, the project expense categories are mastered in Finance and Operations.</span></span> <span data-ttu-id="97f5f-119">Jednak jeśli nie są one zarządzane w programie Finance and Operations lub jeśli kategorie wydatków zostały już utworzone w programie Project Service Automation, należy je najpierw zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops).</span><span class="sxs-lookup"><span data-stu-id="97f5f-119">However, if they aren't mastered in Finance and Operations, or if expense categories have already been created in Project Service Automation, you must first synchronize by using the Project expense transaction categories (PSA to Fin and Ops) template.</span></span> <span data-ttu-id="97f5f-120">Następnie należy wykonać synchronizację przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA).</span><span class="sxs-lookup"><span data-stu-id="97f5f-120">Then synchronize by using the Project expense transaction categories (Fin and Ops to PSA) template.</span></span> <span data-ttu-id="97f5f-121">Następnie należy wykonać jeszcze jedną synchronizację z programu Project Service Automation do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-121">You should then run the synchronization from Project Service Automation to Finance and Operations one more time.</span></span>
>
> <span data-ttu-id="97f5f-122">Jeśli synchronizujesz najpierw z programu Project Service Automation, następujące wymagania muszą być spełnione w programie Finance and Operations przed uruchomieniem synchronizacji:</span><span class="sxs-lookup"><span data-stu-id="97f5f-122">If you synchronize first from Project Service Automation, the following requirements must be met in Finance and Operations before the synchronization is run:</span></span>
>
> - <span data-ttu-id="97f5f-123">Udostępniona kategoria, która pasuje do kategorii projektu skonfigurowanej w programie Project Service Automation, musi istnieć oraz mieć włączone opcje **Projekt** i **Wydatek**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-123">The shared category that matches the project category that is set up in Project Service Automation must exist, and it must be enabled for both **Project** and **Expense**.</span></span>
> - <span data-ttu-id="97f5f-124">Dla każdej firmy, z którą ma być integrowany program Finance and Operations, muszą istnieć następujące kategorie projektu:</span><span class="sxs-lookup"><span data-stu-id="97f5f-124">For each Finance and Operations legal entity that must be integrated with, the following project categories must exist:</span></span>
>
>     - <span data-ttu-id="97f5f-125">Element **Kategoria projektu** istnieje.</span><span class="sxs-lookup"><span data-stu-id="97f5f-125">**Project category** exists.</span></span> 
>     - <span data-ttu-id="97f5f-126">Opcja **Użyj w module wydatków** jest włączona.</span><span class="sxs-lookup"><span data-stu-id="97f5f-126">**Use in Expense** is enabled.</span></span>
>     - <span data-ttu-id="97f5f-127">Opcja **Aktywne w arkuszu** jest włączona.</span><span class="sxs-lookup"><span data-stu-id="97f5f-127">**Active in journal** is enabled.</span></span>
>     - <span data-ttu-id="97f5f-128">W ustawieniu **Typ transakcji** zaznaczono opcję **Wydatek**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-128">**Transaction type** is set to **Expense**.</span></span>

<span data-ttu-id="97f5f-129">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="97f5f-129">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="97f5f-130">[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="97f5f-130">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>

## <a name="project-expense-category-synchronization-from-finance-and-operations-to-project-service-automation"></a><span data-ttu-id="97f5f-131">Synchronizowanie kategorii wydatków w projekcie z programu Finance and Operations do programu Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="97f5f-131">Project expense category synchronization from Finance and Operations to Project Service Automation</span></span>

### <a name="template-and-task"></a><span data-ttu-id="97f5f-132">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="97f5f-132">Template and task</span></span>

<span data-ttu-id="97f5f-133">Aby uzyskać dostęp do szablonu, w centrum administracyjnym usługi Microsoft PowerApps wybierz opcję **Projekty** i w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać spośród szablonów publicznych.</span><span class="sxs-lookup"><span data-stu-id="97f5f-133">To access the template, in the Microsoft PowerApps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="97f5f-134">Następujący szablon i podstawowe zadania służą do synchronizowania kategorii wydatków projektu z rozwiązania Finance and Operations do rozwiązania Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="97f5f-134">The following template and underlying task are used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

- <span data-ttu-id="97f5f-135">**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA)</span><span class="sxs-lookup"><span data-stu-id="97f5f-135">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
- <span data-ttu-id="97f5f-136">**Nazwa zadania w projekcie:** Synchronizowanie kategorii do PSA</span><span class="sxs-lookup"><span data-stu-id="97f5f-136">**Name of the task in the project:** Sync categories to PSA</span></span>

### <a name="entity-set"></a><span data-ttu-id="97f5f-137">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="97f5f-137">Entity set</span></span>

| <span data-ttu-id="97f5f-138">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="97f5f-138">Finance and Operations</span></span>            | <span data-ttu-id="97f5f-139">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="97f5f-139">Project Service Automation</span></span> |
|-----------------------------------|----------------------------|
| <span data-ttu-id="97f5f-140">Jednostka integracji kategorii</span><span class="sxs-lookup"><span data-stu-id="97f5f-140">Integration entity for categories</span></span> | <span data-ttu-id="97f5f-141">Kategorie transakcji</span><span class="sxs-lookup"><span data-stu-id="97f5f-141">Transaction categories</span></span>     |

### <a name="entity-flow"></a><span data-ttu-id="97f5f-142">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="97f5f-142">Entity flow</span></span>

<span data-ttu-id="97f5f-143">Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="97f5f-143">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

### <a name="power-query"></a><span data-ttu-id="97f5f-144">Zapytanie zaawansowane</span><span class="sxs-lookup"><span data-stu-id="97f5f-144">Power Query</span></span>

<span data-ttu-id="97f5f-145">Jeżeli synchronizujesz z rozwiązania Project Service Automation, należy za pomocą dodatku Microsoft Power Query dla programu Excel ustawić typ fakturowania w kategorii transakcji.</span><span class="sxs-lookup"><span data-stu-id="97f5f-145">When you're synchronizing to Project Service Automation, you must use Microsoft Power Query for Excel to set the billing type on the transaction category.</span></span> <span data-ttu-id="97f5f-146">Szablon Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA) zawiera domyślną kolumnę i mapowanie.</span><span class="sxs-lookup"><span data-stu-id="97f5f-146">The Project expense transaction categories (Fin and Ops to PSA) template provides a default column and mapping.</span></span> <span data-ttu-id="97f5f-147">Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową w narzędziu Power Query.</span><span class="sxs-lookup"><span data-stu-id="97f5f-147">If you create your own template, you must add a conditional column in Power Query.</span></span> <span data-ttu-id="97f5f-148">Wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="97f5f-148">Follow these steps.</span></span>

1. <span data-ttu-id="97f5f-149">Kliknij strzałkę, aby otworzyć mapowanie zadania kategorie wydatków w projekcie w szablonie Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA).</span><span class="sxs-lookup"><span data-stu-id="97f5f-149">Click the arrow to open the mapping of the project expense categories task in the Project expense transaction categories (Fin and Ops to PSA) template.</span></span>
2. <span data-ttu-id="97f5f-150">Kliknij łącze **Zaawansowane zapytania i filtrowanie**, aby otworzyć aplikację Power Query.</span><span class="sxs-lookup"><span data-stu-id="97f5f-150">Click the **Advance Query and Filtering** link to open Power Query.</span></span>
2. <span data-ttu-id="97f5f-151">Wybierz opcję **Dodaj kolumnę warunkową**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-151">Select **Add Conditional Column**.</span></span>
3. <span data-ttu-id="97f5f-152">Nadaj nazwę nowej kolumnie, taką jak **BillingType**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-152">Enter a name for the new column, such as **BillingType**.</span></span>
4. <span data-ttu-id="97f5f-153">Wprowadź następujący warunek: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-153">Enter the following condition: **if CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
5. <span data-ttu-id="97f5f-154">W kolumnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="97f5f-154">Click **OK** on the column.</span></span>
6. <span data-ttu-id="97f5f-155">Pamiętaj, aby zamapować tę nową kolumnę na stronie mapowania.</span><span class="sxs-lookup"><span data-stu-id="97f5f-155">Be sure to map this new column on the mapping page.</span></span>

<span data-ttu-id="97f5f-156">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="97f5f-156">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="97f5f-157">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="97f5f-157">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="97f5f-158">[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="97f5f-158">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

## <a name="project-expense-category-synchronization-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="97f5f-159">Synchronizowanie kategorii wydatków w projekcie z programu Project Service Automation do programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="97f5f-159">Project expense category synchronization from Project Service Automation to Finance and Operations</span></span>

### <a name="template-and-task"></a><span data-ttu-id="97f5f-160">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="97f5f-160">Template and task</span></span>

<span data-ttu-id="97f5f-161">Następujący szablon i podstawowe zadania służą do synchronizowania kategorii wydatków projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="97f5f-161">The following template and underlying task are used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

- <span data-ttu-id="97f5f-162">**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="97f5f-162">**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="97f5f-163">**Nazwa zadania w projekcie:** Synchronizowanie kategorii do Fin Ops</span><span class="sxs-lookup"><span data-stu-id="97f5f-163">**Name of the task in the project:** Sync categories to Fin Ops</span></span>

### <a name="entity-set"></a><span data-ttu-id="97f5f-164">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="97f5f-164">Entity set</span></span>

| <span data-ttu-id="97f5f-165">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="97f5f-165">Project Service Automation</span></span> | <span data-ttu-id="97f5f-166">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="97f5f-166">Finance and Operations</span></span>            |
|----------------------------|-----------------------------------|
| <span data-ttu-id="97f5f-167">Kategorie transakcji</span><span class="sxs-lookup"><span data-stu-id="97f5f-167">Transaction categories</span></span>     | <span data-ttu-id="97f5f-168">Jednostka integracji kategorii</span><span class="sxs-lookup"><span data-stu-id="97f5f-168">Integration entity for categories</span></span> |

### <a name="entity-flow"></a><span data-ttu-id="97f5f-169">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="97f5f-169">Entity flow</span></span>

<span data-ttu-id="97f5f-170">Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="97f5f-170">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="97f5f-171">Ponowna synchronizacja do rozwiązania Finance and Operations aktualizuje kategorię projektu w rozwiązaniu Finance and Operations o identyfikator integracji z rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="97f5f-171">The synchronization back to Finance and Operations updates the project category in Finance and Operations with the integration ID from Project Service Automation.</span></span>

### <a name="template-mapping-in-data-integration"></a><span data-ttu-id="97f5f-172">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="97f5f-172">Template mapping in Data integration</span></span>

<span data-ttu-id="97f5f-173">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="97f5f-173">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="97f5f-174">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="97f5f-174">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="97f5f-175">[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="97f5f-175">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

