---
title: "Synchronizowanie kategorii wydatków w projekcie z aplikacji Project Service Automation"
description: "Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: dcdb9b6ec296073d511c069cdceb1c61080b6d97
ms.contentlocale: pl-pl
ms.lasthandoff: 05/29/2018

---

# <a name="synchronize-project-expense-categories-between-finance-and-operations-and-project-service-automation"></a><span data-ttu-id="f2bd0-103">Synchronizowanie kategorii wydatków w projekcie między programami Finance and Operations i Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f2bd0-103">Synchronize project expense categories between Finance and Operations and Project Service Automation</span></span>

<span data-ttu-id="f2bd0-104">Ten temat zawiera opis szablonów i podstawowych zadań, które są używane do synchronizowania kategorii wydatków projektu bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations a programem Microsoft Dynamics 365 for Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-104">This topic describes the templates and underlying tasks that are used to synchronize project expense categories between Microsoft Dynamics 365 for Finance and Operations and Dynamics 365 for Project Service Automation.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bd0-105">Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Dynamics 365 for Finance and Operations w wersji 8.0.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-and-finance-and-operations"></a><span data-ttu-id="f2bd0-106">Przepływ danych między programami Project Service Automation i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f2bd0-106">Data flow for Project Service Automation and Finance and Operations</span></span>

<span data-ttu-id="f2bd0-107">Rozwiązanie integracji rozwiązania Project Service Automation oraz Finance and Operations korzysta z funkcji integracji danych do synchronizowania danych między wystąpieniami rozwiązania Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-107">The Project Service Automation and Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="f2bd0-108">Szablony integracji, które są dostępne z funkcji integracji danych, umożliwiają przepływ danych dotyczących kategorii transakcji wydatkowych w projektach pomiędzy rozwiązaniem Project Service Automation i rozwiązaniem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-108">The integration templates that are available with the Data integration feature enables the flow of data about project expense transaction categories between Finance and Operations and Project Service Automation.</span></span>

<span data-ttu-id="f2bd0-109">Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Finance and Operations, przepływ integracji następuje najpierw z programu Finance and Operations do programu Project Service Automation, po czym są aktualizowane identyfikatory integracji kategorii wydatków w projekcie poprzez synchronizację z programu Project Service Automation do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-109">If the project expense categories are mastered in Finance and Operations, the integration flow is first from Finance and Operations to Project Service Automation, and then updating the project expense categories integration IDs by synchronizing from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="f2bd0-110">Jeśli zarządzanie kategoriami wydatków w projekcie odbywa się w programie Project Service Automation, przepływ integracji następuje najpierw z programu Project Service Automation do programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-110">If the project expense categories are mastered in Project Service Automation, the integration flow is first from Project Service Automation to Finance and Operations.</span></span> <span data-ttu-id="f2bd0-111">Kategorie projektu muszą być skonfigurowane w rozwiązaniu Finance and Operations przed synchronizacją z rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-111">The project categories must already be configured in Finance and Operations prior to the synchronization from Project Service Automation.</span></span> <span data-ttu-id="f2bd0-112">Następnie przeprowadź synchronizację z rozwiązania Finance and Operations ponownie do rozwiązania Project Service Automation, a następnie jeszcze raz z rozwiązania Project Service Automation do rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-112">Then synchronize from Finance and Operations back to Project Service Automation and then from Project Service Automation to Finance and Operations again.</span></span> <span data-ttu-id="f2bd0-113">Dzięki temu kategorie są połączone i duplikaty nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-113">This ensures the categories are linked and duplicates are not created.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bd0-114">Na ogół kategorie wydatków projektu będą zarządzane w Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-114">Typically, the project expense categories will be mastered in Finance and Operations.</span></span> <span data-ttu-id="f2bd0-115">Jeśli w Twojej firmie tak nie jest albo masz już utworzone kategorie wydatków w aplikacji Project Service Automation, należy najpierw zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops), a następnie zsynchronizować przy użyciu szablonu Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA).</span><span class="sxs-lookup"><span data-stu-id="f2bd0-115">If that is not your situation, or you already have expense categories created in Project Service Automation, you must first sync using the Project expense transaction categories (PSA to Fin and Ops) and then sync using Project expense transaction categories (Fin and Ops to PSA).</span></span> <span data-ttu-id="f2bd0-116">Należy następnie uruchomić proces synchronizacji z PSA do rozwiązania Fin and Ops jeszcze raz.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-116">You should then run the sync from PSA to Fin and Ops one more time.</span></span>

> <span data-ttu-id="f2bd0-117">Jeśli synchronizujesz najpierw z programu Project Service Automation, kategorie projektu muszą już być skonfigurowana w programie Finance and Operations, a wszystkie kategorie projektów, które mają być synchronizowane z kategoriami transakcji w programie Project Service Automation, muszą mieć ustawioną opcję **Aktywne w arkuszach**.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-117">If synchronizing first from Project Service Automation, the project categories must already be set up in Finance and Operations and any project categories that need to be synched with the Project Service Automation transaction categories must be set up to be **Active in journals**.</span></span>

<span data-ttu-id="f2bd0-118">Na poniższej ilustracji przedstawiono, w jaki sposób dane są synchronizowane pomiędzy rozwiązaniami Project Service Automation oraz Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-118">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="f2bd0-119">[![Przepływ danych w integracji programu Project Service Automation z programem Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span><span class="sxs-lookup"><span data-stu-id="f2bd0-119">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectExpenseCategoriesFlow.png)](./media/ProjectExpenseCategoriesFlow.png)</span></span>


## <a name="templates-and-tasks"></a><span data-ttu-id="f2bd0-120">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="f2bd0-120">Templates and tasks</span></span>

<span data-ttu-id="f2bd0-121">Aby uzyskać dostęp do dostępnych szablonów w Microsoft PowerApps Admin Center, wybierz **Projekty** i w prawym górnym rogu wybierz **Nowy projekt**, aby wybierać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-121">To access available templates, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="f2bd0-122">Następujący szablon i zadania podrzędne służy do synchronizowania kategorii wydatków projektu z rozwiązania Finance and Operations do rozwiązania Project Service Automation:</span><span class="sxs-lookup"><span data-stu-id="f2bd0-122">The following template and underlying task is used to synchronize project expense categories from Finance and Operations to Project Service Automation:</span></span>

-  <span data-ttu-id="f2bd0-123">**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA)</span><span class="sxs-lookup"><span data-stu-id="f2bd0-123">**Name of the template in Data integration:** Project expense transaction categories (Fin and Ops to PSA)</span></span>
-  <span data-ttu-id="f2bd0-124">**Nazwa zadania w projekcie:** Synchronizowanie kategorii do PSA</span><span class="sxs-lookup"><span data-stu-id="f2bd0-124">**Name of the task in the project:** Sync categories to PSA</span></span>

## <a name="entity-set"></a><span data-ttu-id="f2bd0-125">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="f2bd0-125">Entity set</span></span>

| <span data-ttu-id="f2bd0-126">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f2bd0-126">Finance and Operations</span></span>               | <span data-ttu-id="f2bd0-127">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f2bd0-127">Project Service Automation</span></span>    |
|--------------------------------------|-------------------------------|
| <span data-ttu-id="f2bd0-128">Jednostka integracji kategorii</span><span class="sxs-lookup"><span data-stu-id="f2bd0-128">Integration entity for categories</span></span>    | <span data-ttu-id="f2bd0-129">Kategorie transakcji</span><span class="sxs-lookup"><span data-stu-id="f2bd0-129">Transaction categories</span></span>        |

## <a name="entity-flow"></a><span data-ttu-id="f2bd0-130">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="f2bd0-130">Entity flow</span></span>

<span data-ttu-id="f2bd0-131">Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-131">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span>

## <a name="power-query"></a><span data-ttu-id="f2bd0-132">Zapytanie zaawansowane</span><span class="sxs-lookup"><span data-stu-id="f2bd0-132">Power Query</span></span>

<span data-ttu-id="f2bd0-133">Należy użyć programu Microsoft Power Query w celu ustawienia typu fakturowania w kategorii transakcji podczas synchronizacji z rozwiązaniem Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-133">You must use Microsoft Power Query to set the billing type on the transaction category when synchronizing to Project Service Automation.</span></span> <span data-ttu-id="f2bd0-134">Szablon Kategorie transakcji wydatkowych w projekcie (Fin and Ops do PSA) ma domyślną kolumnę i dostarczone mapowania.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-134">The Project expense transaction categories (Fin and Ops to PSA) template has a default column and mapping already provided.</span></span> <span data-ttu-id="f2bd0-135">Jeśli tworzysz własny szablon, musisz dodać tę kolumnę warunkową w narzędziu Power Query.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-135">If you create your own template, you must add a conditional column in Power Query.</span></span>
- <span data-ttu-id="f2bd0-136">Otwórz formularz Zaawansowane zapytania i filtrowanie z poziomu mapowania zadania kategorii wydatków w projekcie.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-136">Open the Advance Query and Filtering form from within the mapping of project expense categories task.</span></span>
- <span data-ttu-id="f2bd0-137">Wybierz opcję **Dodaj kolumnę warunkową**.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-137">Select **Add Conditional Column**.</span></span>
- <span data-ttu-id="f2bd0-138">Nadaj nowej kolumnie nazwę, taką jak BillingType.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-138">Give the new column a name, such as BillingType.</span></span>
- <span data-ttu-id="f2bd0-139">Wprowadź następujący warunek: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-139">Enter the following condition: if **CATEGORYID not equal to null then 19235001, Otherwise null**.</span></span>
- <span data-ttu-id="f2bd0-140">W kolumnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-140">Click **OK** on the column.</span></span>
- <span data-ttu-id="f2bd0-141">Pamiętaj, aby zamapować tę nową kolumnę na stronie mapowania.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-141">Be sure to map this new column in the mapping page.</span></span>

<span data-ttu-id="f2bd0-142">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-142">The following illustration shows an example of the template task mapping in Data integration.</span></span> <span data-ttu-id="f2bd0-143">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-143">The mapping shows the field information that will be synchronized from Finance and Operations to Project Service Automation.</span></span>

<span data-ttu-id="f2bd0-144">[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="f2bd0-144">[![Template mapping](./media/ProjectExpenseCategoriesToPSAMapping.jpg)](./media/ProjectExpenseCategoriesToPSAMapping.jpg)</span></span>

<span data-ttu-id="f2bd0-145">Następujący szablon i zadanie podrzędne służy do synchronizowania kategorii wydatków projektu z rozwiązania Project Service Automation do rozwiązania Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="f2bd0-145">The following template and underlying task is used to synchronize project expense categories from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="f2bd0-146">-**Nazwa szablonu w narzędziu Integracja danych:** Kategorie transakcji wydatkowych w projekcie (PSA do Fin and Ops) -**Nazwa zadania w projekcie:** Synchronizowanie kategorii do Fin Ops</span><span class="sxs-lookup"><span data-stu-id="f2bd0-146">-**Name of the template in Data integration:** Project expense transaction categories (PSA to Fin and Ops) -**Name of the task in the project:** Sync categories to Fin Ops</span></span>

## <a name="entity-set"></a><span data-ttu-id="f2bd0-147">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="f2bd0-147">Entity set</span></span>

| <span data-ttu-id="f2bd0-148">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f2bd0-148">Project Service Automation</span></span>      | <span data-ttu-id="f2bd0-149">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f2bd0-149">Finance and Operations</span></span>             |
|---------------------------------|------------------------------------|
| <span data-ttu-id="f2bd0-150">Kategorie transakcji</span><span class="sxs-lookup"><span data-stu-id="f2bd0-150">Transaction categories</span></span>          | <span data-ttu-id="f2bd0-151">Jednostka integracji kategorii</span><span class="sxs-lookup"><span data-stu-id="f2bd0-151">Integration entity for categories</span></span>  | 

## <a name="entity-flow"></a><span data-ttu-id="f2bd0-152">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="f2bd0-152">Entity flow</span></span>

<span data-ttu-id="f2bd0-153">Zarządzanie kategoriami wydatków w projekcie odbywa się w aplikacji Finance and Operations i są one synchronizowane z aplikacją Project Service Automation jako kategorie transakcji.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-153">Project expense categories are managed in Finance and Operations, and they are synchronized to Project Service Automation as transaction categories.</span></span> <span data-ttu-id="f2bd0-154">Ponowna synchronizacja do rozwiązania Finance and Operations aktualizuje identyfikator integracji z rozwiązania Project Service Automation w kategorii projektów rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-154">The synchronization back to Finance and Operations updates the integration ID from Project Service Automation on the Finance and Operations project category.</span></span>

<span data-ttu-id="f2bd0-155">Poniższa ilustracja przedstawia przykład mapowania zadań szablonu w integracji danych.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-155">The following illustration shows an example of the template task mapping in Data integration.</span></span>

> [!NOTE]
> <span data-ttu-id="f2bd0-156">Mapowanie pokazuje informacje z pola, które zostanie zsynchronizowane z rozwiązania Finance and Operations do rozwiązania Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="f2bd0-156">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="f2bd0-157">[![Mapowanie szablonu](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span><span class="sxs-lookup"><span data-stu-id="f2bd0-157">[![Template mapping](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)](./media/ProjectExpenseCategoriesToFinOpsMapping.jpg)</span></span>

