---
title: Definiowanie zasad inspekcji dla dokumentów źródłowych
description: W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 17b712f07a0ffe6874eb6d98b47ced96f5a54483
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846494"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="51337-103">Definiowanie zasad inspekcji dla dokumentów źródłowych</span><span class="sxs-lookup"><span data-stu-id="51337-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="51337-104">W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji.</span><span class="sxs-lookup"><span data-stu-id="51337-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="51337-105">W przykładzie użyto raportów z wydatków hotelowych.</span><span class="sxs-lookup"><span data-stu-id="51337-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="51337-106">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="51337-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="51337-107">Rola audytora zawiera odpowiednie uprawnienia niezbędne do wykonania tych zadań.</span><span class="sxs-lookup"><span data-stu-id="51337-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="51337-108">Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Typ reguły.</span><span class="sxs-lookup"><span data-stu-id="51337-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="51337-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="51337-109">Click New.</span></span>
3. <span data-ttu-id="51337-110">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="51337-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="51337-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="51337-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="51337-112">W polu Nazwa kwerendy wybierz opcję Wiersz raportu wydatków.</span><span class="sxs-lookup"><span data-stu-id="51337-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="51337-113">W polu typu kwerendy wybierz opcję Agregacja.</span><span class="sxs-lookup"><span data-stu-id="51337-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="51337-114">W polu Firma wybierz firmę.</span><span class="sxs-lookup"><span data-stu-id="51337-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="51337-115">W polu Odwołanie do daty dokumentu wybierz opcję Data i godzina modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="51337-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="51337-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="51337-116">Click Save.</span></span>
10. <span data-ttu-id="51337-117">Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Zasady inspekcji.</span><span class="sxs-lookup"><span data-stu-id="51337-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="51337-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="51337-118">Click New.</span></span>
12. <span data-ttu-id="51337-119">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="51337-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="51337-120">Rozwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="51337-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="51337-121">W drzewie zaznacz pozycję „Contoso Entertainment System USA”.</span><span class="sxs-lookup"><span data-stu-id="51337-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="51337-122">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-122">Click Add.</span></span>
16. <span data-ttu-id="51337-123">W drzewie zaznacz pozycję „Contoso Consulting USA”.</span><span class="sxs-lookup"><span data-stu-id="51337-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="51337-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-124">Click Add.</span></span>
18. <span data-ttu-id="51337-125">W drzewie zaznacz pozycję „Contoso Retail USA”.</span><span class="sxs-lookup"><span data-stu-id="51337-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="51337-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-126">Click Add.</span></span>
20. <span data-ttu-id="51337-127">Zwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="51337-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="51337-128">Rozwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="51337-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="51337-129">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="51337-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="51337-130">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="51337-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="51337-131">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="51337-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="51337-132">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="51337-132">Click Filter.</span></span>
26. <span data-ttu-id="51337-133">Na liście zaznacz wiersz kategorii wydatku oraz ustaw szczegóły dotyczące hotelu.</span><span class="sxs-lookup"><span data-stu-id="51337-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="51337-134">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51337-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="51337-135">Kliknij kartę Agregacja.</span><span class="sxs-lookup"><span data-stu-id="51337-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="51337-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-136">Click Add.</span></span>
30. <span data-ttu-id="51337-137">Na liście zaznacz wartość Kwota transakcji.</span><span class="sxs-lookup"><span data-stu-id="51337-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="51337-138">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51337-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="51337-139">W polu Funkcja agregująca wybierz opcję „Suma”.</span><span class="sxs-lookup"><span data-stu-id="51337-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="51337-140">Kliknij kartę Grupuj wg .</span><span class="sxs-lookup"><span data-stu-id="51337-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="51337-141">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-141">Click Add.</span></span>
35. <span data-ttu-id="51337-142">Na liście zaznacz wartość Pracownik. </span><span class="sxs-lookup"><span data-stu-id="51337-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="51337-143">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-143">Click Add.</span></span>
37. <span data-ttu-id="51337-144">Na liście zaznacz wartość Kategoria wydatku.</span><span class="sxs-lookup"><span data-stu-id="51337-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="51337-145">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51337-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="51337-146">Kliknij kartę Zawiera.</span><span class="sxs-lookup"><span data-stu-id="51337-146">Click the Having tab.</span></span>
40. <span data-ttu-id="51337-147">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="51337-147">Click Add.</span></span>
41. <span data-ttu-id="51337-148">Zaznacz opcję Kwota transakcji.</span><span class="sxs-lookup"><span data-stu-id="51337-148">Select Transaction amount</span></span>
42. <span data-ttu-id="51337-149">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="51337-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="51337-150">W polu Funkcja agregująca wybierz opcję „Suma”.</span><span class="sxs-lookup"><span data-stu-id="51337-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="51337-151">W polu Kryteria wpisz wartość „>2000”.</span><span class="sxs-lookup"><span data-stu-id="51337-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="51337-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51337-152">Click OK.</span></span>
46. <span data-ttu-id="51337-153">Kliknij przycisk Test.</span><span class="sxs-lookup"><span data-stu-id="51337-153">Click Test.</span></span>
47. <span data-ttu-id="51337-154">W polu Data początkowa wyboru dokumentów wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="51337-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="51337-155">W polu Data końcowa wyboru dokumentów wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="51337-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="51337-156">Kliknij przycisk Uruchom test.</span><span class="sxs-lookup"><span data-stu-id="51337-156">Click Run test.</span></span>
50. <span data-ttu-id="51337-157">W okienku akcji kliknij pozycję Zasady inspekcji.</span><span class="sxs-lookup"><span data-stu-id="51337-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="51337-158">Kliknij przycisk Opcje dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="51337-158">Click Additional options.</span></span>
52. <span data-ttu-id="51337-159">W polu Data rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="51337-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="51337-160">W polu Data zakończenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="51337-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="51337-161">Kliknij przycisk Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="51337-161">Click Batch.</span></span>
55. <span data-ttu-id="51337-162">Rozwiń sekcję Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="51337-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="51337-163">W polu Przetwarzanie wsadowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="51337-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="51337-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="51337-164">Click OK.</span></span>
58. <span data-ttu-id="51337-165">Wybierz kolejno opcje Pulpit inspekcji > Sprawy inspekcji.</span><span class="sxs-lookup"><span data-stu-id="51337-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="51337-166">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="51337-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="51337-167">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="51337-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="51337-168">Rozwiń sekcję Powiązania.</span><span class="sxs-lookup"><span data-stu-id="51337-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="51337-169">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="51337-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="51337-170">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="51337-170">In the list, click the link in the selected row.</span></span>

