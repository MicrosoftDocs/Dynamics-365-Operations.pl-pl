---
title: Definiowanie zasad audytu dla dokumentów źródłowych
description: W tym temacie pokazano sposób konfigurowania i uruchamiania reguł inspekcji.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6b0fa28d778a4d9fa1f718b1d50bf1dce00be00
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914843"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="6e26a-103">Definiowanie zasad audytu dla dokumentów źródłowych</span><span class="sxs-lookup"><span data-stu-id="6e26a-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e26a-104">W tym temacie pokazano sposób konfigurowania i uruchamiania reguł inspekcji.</span><span class="sxs-lookup"><span data-stu-id="6e26a-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="6e26a-105">W przykładzie użyto raportów z wydatków hotelowych.</span><span class="sxs-lookup"><span data-stu-id="6e26a-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="6e26a-106">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="6e26a-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="6e26a-107">Rola audytora zawiera odpowiednie uprawnienia niezbędne do wykonania tych zadań.</span><span class="sxs-lookup"><span data-stu-id="6e26a-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="6e26a-108">W okienku nawigacji przejdź do **Moduły > Pulpit inspekcji > Ustawienia > Typ reguły**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="6e26a-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-109">Select **New**.</span></span>
3. <span data-ttu-id="6e26a-110">W polu **Nazwa reguły** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="6e26a-111">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="6e26a-112">W polu **Nazwa kwerendy** wybierz opcję **Wiersz raportu wydatków**</span><span class="sxs-lookup"><span data-stu-id="6e26a-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="6e26a-113">W polu **typ kwerendy** wybierz opcję **Agregacja**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="6e26a-114">W polu **Firma** wybierz **firmę**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="6e26a-115">W polu **Odwołanie do daty dokumentu** wybierz opcję **Data i godzina modyfikacji**</span><span class="sxs-lookup"><span data-stu-id="6e26a-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="6e26a-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-116">Select **Save**.</span></span>
10. <span data-ttu-id="6e26a-117">W okienku nawigacji przejdź do **Moduły > Pulpit inspekcji > Ustawienia > Zasady inspekcji**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="6e26a-118">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-118">Select **New**.</span></span>
12. <span data-ttu-id="6e26a-119">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="6e26a-120">Rozwiń sekcję **Organizacje zasad**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="6e26a-121">W drzewie zaznacz pozycję **Contoso Entertainment System USA**, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="6e26a-122">W drzewie zaznacz pozycję **Contoso Consulting USA**, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="6e26a-123">W drzewie zaznacz pozycję **Contoso Retail USA**, a następnie wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="6e26a-124">Zwiń sekcję **Organizacje zasad**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="6e26a-125">Rozwiń sekcję **Reguły zasad**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="6e26a-126">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="6e26a-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="6e26a-127">Wybierz pozycję **Utwórz regułę**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="6e26a-128">W polu **Data obowiązywania** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6e26a-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="6e26a-129">Wybierz **Filtry**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-129">Select **Filter**.</span></span>
23. <span data-ttu-id="6e26a-130">Na liście zaznacz wiersz **kategorii wydatku** oraz ustaw szczegóły dotyczące **hotelu**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="6e26a-131">W polu **Kryteria** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="6e26a-132">Wybierz kartę **Agreguj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="6e26a-133">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-133">Select **Add**.</span></span>
27. <span data-ttu-id="6e26a-134">Na liście zaznacz wartość **Kwota transakcji**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="6e26a-135">W polu **Pole** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="6e26a-136">W polu **Funkcja agregująca** wybierz opcję **Suma**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="6e26a-137">Wybierz kartę **Grupuj wg**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="6e26a-138">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-138">Select **Add**.</span></span>
32. <span data-ttu-id="6e26a-139">Na liście zaznacz wartość **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="6e26a-140">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-140">Select **Add**.</span></span>
34. <span data-ttu-id="6e26a-141">Na liście zaznacz wartość **Kategoria wydatku**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="6e26a-142">W polu **Pole** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="6e26a-143">Kliknij kartę **Posiadanie**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="6e26a-144">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-144">Select **Add**.</span></span>
38. <span data-ttu-id="6e26a-145">Zaznacz opcję **Kwota transakcji**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="6e26a-146">W polu **Pole** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="6e26a-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="6e26a-147">W polu **Funkcja agregująca** wybierz opcję **Suma**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="6e26a-148">W polu **Kryteria** wpisz wartość `>2000`.</span><span class="sxs-lookup"><span data-stu-id="6e26a-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="6e26a-149">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-149">Select **OK**.</span></span>
43. <span data-ttu-id="6e26a-150">Wybierz **test**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-150">Select **Test**.</span></span>
44. <span data-ttu-id="6e26a-151">W polu **Data początkowa wyboru dokumentów** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6e26a-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="6e26a-152">W polu **Data końcowa wyboru dokumentów** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6e26a-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="6e26a-153">Wybierz **Uruchamianie przypadków testowych**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-153">Select **Run test**.</span></span>
47. <span data-ttu-id="6e26a-154">W okienku akcji kliknij pozycję **Zasady inspekcji**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="6e26a-155">Wybierz **Opcje dodatkowe**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="6e26a-156">W polu **Data rozpoczęcia** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6e26a-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="6e26a-157">W polu **Data zakończenia** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="6e26a-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="6e26a-158">Wybierz **Partia**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-158">Select **Batch**.</span></span>
52. <span data-ttu-id="6e26a-159">Rozwiń sekcję **Uruchom w tle**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="6e26a-160">W polu **Przetwarzanie wsadowe** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="6e26a-161">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-161">Select **OK**.</span></span>
55. <span data-ttu-id="6e26a-162">W okienku nawigacji przejdź do **Moduły > Pulpit inspekcji > Sprawy inspekcji**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="6e26a-163">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6e26a-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="6e26a-164">Rozwiń sekcję **Powiązania**.</span><span class="sxs-lookup"><span data-stu-id="6e26a-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="6e26a-165">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6e26a-165">In the list, find and select the desired record.</span></span>

