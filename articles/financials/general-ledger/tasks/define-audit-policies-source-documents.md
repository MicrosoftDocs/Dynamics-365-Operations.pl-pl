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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="247c3-103">Definiowanie zasad inspekcji dla dokumentów źródłowych</span><span class="sxs-lookup"><span data-stu-id="247c3-103">Define audit policies for source documents</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="247c3-104">W tej procedurze pokazano sposób konfigurowania i uruchamiania reguł inspekcji.</span><span class="sxs-lookup"><span data-stu-id="247c3-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="247c3-105">W przykładzie użyto raportów z wydatków hotelowych.</span><span class="sxs-lookup"><span data-stu-id="247c3-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="247c3-106">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="247c3-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="247c3-107">Rola audytora zawiera odpowiednie uprawnienia niezbędne do wykonania tych zadań.</span><span class="sxs-lookup"><span data-stu-id="247c3-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="247c3-108">Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Typ reguły.</span><span class="sxs-lookup"><span data-stu-id="247c3-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="247c3-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="247c3-109">Click New.</span></span>
3. <span data-ttu-id="247c3-110">W polu Nazwa reguły wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="247c3-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="247c3-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="247c3-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="247c3-112">W polu Nazwa kwerendy wybierz opcję Wiersz raportu wydatków.</span><span class="sxs-lookup"><span data-stu-id="247c3-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="247c3-113">W polu typu kwerendy wybierz opcję Agregacja.</span><span class="sxs-lookup"><span data-stu-id="247c3-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="247c3-114">W polu Firma wybierz firmę.</span><span class="sxs-lookup"><span data-stu-id="247c3-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="247c3-115">W polu Odwołanie do daty dokumentu wybierz opcję Data i godzina modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="247c3-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="247c3-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="247c3-116">Click Save.</span></span>
10. <span data-ttu-id="247c3-117">Wybierz kolejno opcje Pulpit inspekcji > Ustawienia > Zasady inspekcji.</span><span class="sxs-lookup"><span data-stu-id="247c3-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="247c3-118">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="247c3-118">Click New.</span></span>
12. <span data-ttu-id="247c3-119">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="247c3-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="247c3-120">Rozwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="247c3-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="247c3-121">W drzewie zaznacz pozycję „Contoso Entertainment System USA”.</span><span class="sxs-lookup"><span data-stu-id="247c3-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="247c3-122">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-122">Click Add.</span></span>
16. <span data-ttu-id="247c3-123">W drzewie zaznacz pozycję „Contoso Consulting USA”.</span><span class="sxs-lookup"><span data-stu-id="247c3-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="247c3-124">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-124">Click Add.</span></span>
18. <span data-ttu-id="247c3-125">W drzewie zaznacz pozycję „Contoso Retail USA”.</span><span class="sxs-lookup"><span data-stu-id="247c3-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="247c3-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-126">Click Add.</span></span>
20. <span data-ttu-id="247c3-127">Zwiń sekcję Organizacje zasad.</span><span class="sxs-lookup"><span data-stu-id="247c3-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="247c3-128">Rozwiń sekcję Reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="247c3-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="247c3-129">Na liście znajdź i zaznacz regułę, która została wcześniej utworzona.</span><span class="sxs-lookup"><span data-stu-id="247c3-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="247c3-130">Kliknij przycisk Utwórz regułę.</span><span class="sxs-lookup"><span data-stu-id="247c3-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="247c3-131">W polu Data obowiązywania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="247c3-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="247c3-132">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="247c3-132">Click Filter.</span></span>
26. <span data-ttu-id="247c3-133">Na liście zaznacz wiersz kategorii wydatku oraz ustaw szczegóły dotyczące hotelu.</span><span class="sxs-lookup"><span data-stu-id="247c3-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="247c3-134">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="247c3-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="247c3-135">Kliknij kartę Agregacja.</span><span class="sxs-lookup"><span data-stu-id="247c3-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="247c3-136">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-136">Click Add.</span></span>
30. <span data-ttu-id="247c3-137">Na liście zaznacz wartość Kwota transakcji.</span><span class="sxs-lookup"><span data-stu-id="247c3-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="247c3-138">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="247c3-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="247c3-139">W polu Funkcja agregująca wybierz opcję „Suma”.</span><span class="sxs-lookup"><span data-stu-id="247c3-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="247c3-140">Kliknij kartę Grupuj wg .</span><span class="sxs-lookup"><span data-stu-id="247c3-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="247c3-141">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-141">Click Add.</span></span>
35. <span data-ttu-id="247c3-142">Na liście zaznacz wartość Pracownik. </span><span class="sxs-lookup"><span data-stu-id="247c3-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="247c3-143">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-143">Click Add.</span></span>
37. <span data-ttu-id="247c3-144">Na liście zaznacz wartość Kategoria wydatku.</span><span class="sxs-lookup"><span data-stu-id="247c3-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="247c3-145">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="247c3-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="247c3-146">Kliknij kartę Zawiera.</span><span class="sxs-lookup"><span data-stu-id="247c3-146">Click the Having tab.</span></span>
40. <span data-ttu-id="247c3-147">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="247c3-147">Click Add.</span></span>
41. <span data-ttu-id="247c3-148">Zaznacz opcję Kwota transakcji.</span><span class="sxs-lookup"><span data-stu-id="247c3-148">Select Transaction amount</span></span>
42. <span data-ttu-id="247c3-149">W polu Pole wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="247c3-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="247c3-150">W polu Funkcja agregująca wybierz opcję „Suma”.</span><span class="sxs-lookup"><span data-stu-id="247c3-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="247c3-151">W polu Kryteria wpisz wartość „>2000”.</span><span class="sxs-lookup"><span data-stu-id="247c3-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="247c3-152">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="247c3-152">Click OK.</span></span>
46. <span data-ttu-id="247c3-153">Kliknij przycisk Test.</span><span class="sxs-lookup"><span data-stu-id="247c3-153">Click Test.</span></span>
47. <span data-ttu-id="247c3-154">W polu Data początkowa wyboru dokumentów wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="247c3-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="247c3-155">W polu Data końcowa wyboru dokumentów wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="247c3-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="247c3-156">Kliknij przycisk Uruchom test.</span><span class="sxs-lookup"><span data-stu-id="247c3-156">Click Run test.</span></span>
50. <span data-ttu-id="247c3-157">W okienku akcji kliknij pozycję Zasady inspekcji.</span><span class="sxs-lookup"><span data-stu-id="247c3-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="247c3-158">Kliknij przycisk Opcje dodatkowe.</span><span class="sxs-lookup"><span data-stu-id="247c3-158">Click Additional options.</span></span>
52. <span data-ttu-id="247c3-159">W polu Data rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="247c3-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="247c3-160">W polu Data zakończenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="247c3-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="247c3-161">Kliknij przycisk Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="247c3-161">Click Batch.</span></span>
55. <span data-ttu-id="247c3-162">Rozwiń sekcję Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="247c3-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="247c3-163">W polu Przetwarzanie wsadowe zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="247c3-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="247c3-164">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="247c3-164">Click OK.</span></span>
58. <span data-ttu-id="247c3-165">Wybierz kolejno opcje Pulpit inspekcji > Sprawy inspekcji.</span><span class="sxs-lookup"><span data-stu-id="247c3-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="247c3-166">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="247c3-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="247c3-167">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="247c3-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="247c3-168">Rozwiń sekcję Powiązania.</span><span class="sxs-lookup"><span data-stu-id="247c3-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="247c3-169">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="247c3-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="247c3-170">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="247c3-170">In the list, click the link in the selected row.</span></span>


