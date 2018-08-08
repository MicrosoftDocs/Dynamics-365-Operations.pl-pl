--- 
title: Tworzenie hierarchii organizacyjnej raportowania
description: "Ta procedura służy do tworzenia hierarchii raportów dla sprawozdawczości w organizacji."
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: d9a06a67f851e4a73df90f999683d5ea27f38e66
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="7fe36-103">Tworzenie hierarchii organizacyjnej raportowania</span><span class="sxs-lookup"><span data-stu-id="7fe36-103">Create an organization report hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7fe36-104">Ta procedura służy do tworzenia hierarchii raportów dla sprawozdawczości w organizacji.</span><span class="sxs-lookup"><span data-stu-id="7fe36-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="7fe36-105">Celem tego nagrania jest przeprowadzenie użytkownika przez hierarchię wymiarów, tak aby mógł on kontynuować pracę do czasu utworzenia całej struktury raportowania w organizacji.</span><span class="sxs-lookup"><span data-stu-id="7fe36-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="7fe36-106">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="7fe36-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="7fe36-107">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="7fe36-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="7fe36-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-108">Click New.</span></span>
3. <span data-ttu-id="7fe36-109">W polu HierarchyTypeComboBox wybierz opcję „Hierarchia klasyfikacji wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="7fe36-110">Wybierz opcję Hierarchia klasyfikacji wymiarów.</span><span class="sxs-lookup"><span data-stu-id="7fe36-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="7fe36-111">Typ Hierarchia klasyfikacji wymiarów jest używany do definiowania reguł i na potrzeby sprawozdawczości.</span><span class="sxs-lookup"><span data-stu-id="7fe36-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="7fe36-112">Obsługuje wszystkie wymiary, takie jak obiekty kosztów, składniki kosztów i wymiary statystyczne.</span><span class="sxs-lookup"><span data-stu-id="7fe36-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="7fe36-113">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-113">Click Create.</span></span>
5. <span data-ttu-id="7fe36-114">W polu Nazwa hierarchii wymiarów wpisz wartość „Organizacja USP2”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="7fe36-115">W polu Wymiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fe36-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="7fe36-116">Wybierz opcję Centra kosztów.</span><span class="sxs-lookup"><span data-stu-id="7fe36-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="7fe36-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-117">Click Save.</span></span>
8. <span data-ttu-id="7fe36-118">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="7fe36-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="7fe36-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-119">Click New.</span></span>
10. <span data-ttu-id="7fe36-120">W polu Nazwa węzła wpisz „Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="7fe36-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-121">Click Save.</span></span>
12. <span data-ttu-id="7fe36-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-122">Click New.</span></span>
13. <span data-ttu-id="7fe36-123">W polu Nazwa węzła wpisz „Dyrektor generalny Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="7fe36-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-124">Click Save.</span></span>
15. <span data-ttu-id="7fe36-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-125">Click New.</span></span>
16. <span data-ttu-id="7fe36-126">W polu Nazwa węzła wpisz „Region Wschód”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="7fe36-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-127">Click Save.</span></span>
18. <span data-ttu-id="7fe36-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-128">Click New.</span></span>
19. <span data-ttu-id="7fe36-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="7fe36-130">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fe36-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7fe36-131">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="7fe36-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="7fe36-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-132">Click Save.</span></span>
22. <span data-ttu-id="7fe36-133">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny\Dyrektor generalny Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="7fe36-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-134">Click New.</span></span>
24. <span data-ttu-id="7fe36-135">W polu Nazwa węzła wpisz „Region Zachód”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="7fe36-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-136">Click Save.</span></span>
26. <span data-ttu-id="7fe36-137">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-137">Click New.</span></span>
27. <span data-ttu-id="7fe36-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="7fe36-139">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fe36-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7fe36-140">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="7fe36-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="7fe36-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-141">Click Save.</span></span>
30. <span data-ttu-id="7fe36-142">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="7fe36-143">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-143">Click New.</span></span>
32. <span data-ttu-id="7fe36-144">W polu Nazwa węzła wpisz „Dyrektor finansowy Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="7fe36-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-145">Click Save.</span></span>
34. <span data-ttu-id="7fe36-146">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-146">Click New.</span></span>
35. <span data-ttu-id="7fe36-147">W polu Nazwa węzła wpisz „Kampania marketingowa”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="7fe36-148">W polu Nazwa węzła wpisz „Kampania marketingowa”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="7fe36-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-149">Click Save.</span></span>
38. <span data-ttu-id="7fe36-150">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-150">Click New.</span></span>
39. <span data-ttu-id="7fe36-151">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="7fe36-152">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fe36-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7fe36-153">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="7fe36-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="7fe36-154">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-154">Click Save.</span></span>
42. <span data-ttu-id="7fe36-155">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny\Dyrektor finansowy Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="7fe36-156">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-156">Click New.</span></span>
44. <span data-ttu-id="7fe36-157">W polu Nazwa węzła wpisz „Targi”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="7fe36-158">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-158">Click Save.</span></span>
46. <span data-ttu-id="7fe36-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-159">Click New.</span></span>
47. <span data-ttu-id="7fe36-160">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="7fe36-161">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fe36-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7fe36-162">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="7fe36-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="7fe36-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-163">Click Save.</span></span>
50. <span data-ttu-id="7fe36-164">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="7fe36-165">W polu Nazwa węzła wpisz „Dyrektor ds. informatyki Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="7fe36-166">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-166">Click Save.</span></span>
53. <span data-ttu-id="7fe36-167">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-167">Click New.</span></span>
54. <span data-ttu-id="7fe36-168">W polu Nazwa węzła wpisz „Biura obsługi”.</span><span class="sxs-lookup"><span data-stu-id="7fe36-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="7fe36-169">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-169">Click Save.</span></span>
56. <span data-ttu-id="7fe36-170">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fe36-170">Click New.</span></span>
57. <span data-ttu-id="7fe36-171">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="7fe36-172">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fe36-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7fe36-173">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="7fe36-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="7fe36-174">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="7fe36-174">Click Save.</span></span>


