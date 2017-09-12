--- 
title: "Definiowanie zasad inspekcji dla dokumentów źródłowych"
description: "W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji."
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="78c6a-103">Definiowanie zasad inspekcji dla dokumentów źródłowych</span><span class="sxs-lookup"><span data-stu-id="78c6a-103">Define audit policies for source documents</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78c6a-104">W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="78c6a-105">W przykładzie użyto raportów z wydatków hotelowych.</span><span class="sxs-lookup"><span data-stu-id="78c6a-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="78c6a-106">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="78c6a-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="78c6a-107">Rola audytora zawiera odpowiednie uprawnienia niezbędne do wykonania tych zadań.</span><span class="sxs-lookup"><span data-stu-id="78c6a-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="78c6a-108">Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Typ reguły.</span><span class="sxs-lookup"><span data-stu-id="78c6a-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="78c6a-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78c6a-109">Click New.</span></span>
3. <span data-ttu-id="78c6a-110">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="78c6a-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="78c6a-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="78c6a-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="78c6a-112">W polu Nazwa kwerendy wybierz opcję Wiersz raportu wydatków.</span><span class="sxs-lookup"><span data-stu-id="78c6a-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="78c6a-113">W polu typu kwerendy wybierz opcję Agregacja.</span><span class="sxs-lookup"><span data-stu-id="78c6a-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="78c6a-114">W polu Firma wybierz firmę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="78c6a-115">W polu Odwołanie do daty dokumentu wybierz opcję Data i godzina modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="78c6a-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="78c6a-116">Click Save.</span></span>
10. <span data-ttu-id="78c6a-117">Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Zasady inspekcji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="78c6a-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="78c6a-118">Click New.</span></span>
12. <span data-ttu-id="78c6a-119">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="78c6a-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="78c6a-120">Rozwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="78c6a-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="78c6a-121">W drzewie zaznacz pozycję „Contoso Entertainment System USA”.</span><span class="sxs-lookup"><span data-stu-id="78c6a-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="78c6a-122">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-122">Click Add.</span></span>
16. <span data-ttu-id="78c6a-123">W drzewie zaznacz pozycję „Contoso Consulting USA”.</span><span class="sxs-lookup"><span data-stu-id="78c6a-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="78c6a-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-124">Click Add.</span></span>
18. <span data-ttu-id="78c6a-125">W drzewie zaznacz pozycję „Contoso Retail USA”.</span><span class="sxs-lookup"><span data-stu-id="78c6a-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="78c6a-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-126">Click Add.</span></span>
20. <span data-ttu-id="78c6a-127">Zwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="78c6a-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="78c6a-128">Rozwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="78c6a-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="78c6a-129">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="78c6a-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="78c6a-130">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="78c6a-131">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="78c6a-132">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="78c6a-132">Click Filter.</span></span>
26. <span data-ttu-id="78c6a-133">Na liście zaznacz wiersz kategorii wydatku oraz ustaw szczegóły dotyczące hotelu.</span><span class="sxs-lookup"><span data-stu-id="78c6a-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="78c6a-134">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78c6a-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="78c6a-135">Kliknij kartę Agregacja.</span><span class="sxs-lookup"><span data-stu-id="78c6a-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="78c6a-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-136">Click Add.</span></span>
30. <span data-ttu-id="78c6a-137">Na liście zaznacz wartość Kwota transakcji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="78c6a-138">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78c6a-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="78c6a-139">W polu Funkcja agregująca wybierz opcję „Suma”.</span><span class="sxs-lookup"><span data-stu-id="78c6a-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="78c6a-140">Kliknij kartę Grupuj wg .</span><span class="sxs-lookup"><span data-stu-id="78c6a-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="78c6a-141">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-141">Click Add.</span></span>
35. <span data-ttu-id="78c6a-142">Na liście zaznacz wartość Pracownik. </span><span class="sxs-lookup"><span data-stu-id="78c6a-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="78c6a-143">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-143">Click Add.</span></span>
37. <span data-ttu-id="78c6a-144">Na liście zaznacz wartość Kategoria wydatku.</span><span class="sxs-lookup"><span data-stu-id="78c6a-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="78c6a-145">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78c6a-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="78c6a-146">Kliknij kartę Zawiera.</span><span class="sxs-lookup"><span data-stu-id="78c6a-146">Click the Having tab.</span></span>
40. <span data-ttu-id="78c6a-147">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="78c6a-147">Click Add.</span></span>
41. <span data-ttu-id="78c6a-148">Zaznacz opcję Kwota transakcji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-148">Select Transaction amount</span></span>
42. <span data-ttu-id="78c6a-149">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="78c6a-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="78c6a-150">W polu Funkcja agregująca wybierz opcję „Suma”.</span><span class="sxs-lookup"><span data-stu-id="78c6a-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="78c6a-151">W polu Kryteria wpisz wartość „>2000”.</span><span class="sxs-lookup"><span data-stu-id="78c6a-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="78c6a-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="78c6a-152">Click OK.</span></span>
46. <span data-ttu-id="78c6a-153">Kliknij przycisk Test.</span><span class="sxs-lookup"><span data-stu-id="78c6a-153">Click Test.</span></span>
47. <span data-ttu-id="78c6a-154">W polu Data początkowa wyboru dokumentów wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="78c6a-155">W polu Data końcowa wyboru dokumentów wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="78c6a-156">Kliknij przycisk Uruchom test.</span><span class="sxs-lookup"><span data-stu-id="78c6a-156">Click Run test.</span></span>
50. <span data-ttu-id="78c6a-157">W okienku akcji kliknij pozycję Zasady inspekcji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="78c6a-158">Kliknij przycisk Opcje dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="78c6a-158">Click Additional options.</span></span>
52. <span data-ttu-id="78c6a-159">W polu Data rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="78c6a-160">W polu Data zakończenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="78c6a-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="78c6a-161">Kliknij przycisk Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="78c6a-161">Click Batch.</span></span>
55. <span data-ttu-id="78c6a-162">Rozwiń sekcję Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="78c6a-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="78c6a-163">W polu Przetwarzanie wsadowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="78c6a-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="78c6a-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="78c6a-164">Click OK.</span></span>
58. <span data-ttu-id="78c6a-165">Wybierz kolejno opcje Pulpit inspekcji > Sprawy inspekcji.</span><span class="sxs-lookup"><span data-stu-id="78c6a-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="78c6a-166">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78c6a-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="78c6a-167">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="78c6a-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="78c6a-168">Rozwiń sekcję Powiązania.</span><span class="sxs-lookup"><span data-stu-id="78c6a-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="78c6a-169">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="78c6a-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="78c6a-170">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="78c6a-170">In the list, click the link in the selected row.</span></span>


