--- 
title: Tworzenie hierarchii organizacyjnej raportowania
description: "Ta procedura służy do tworzenia hierarchii raportów dla sprawozdawczości w organizacji."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f593c59660abcf5b0d5771ddd9daced6ec5fbfb4
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="f60be-103">Tworzenie hierarchii organizacyjnej raportowania</span><span class="sxs-lookup"><span data-stu-id="f60be-103">Create an organization report hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f60be-104">Ta procedura służy do tworzenia hierarchii raportów dla sprawozdawczości w organizacji.</span><span class="sxs-lookup"><span data-stu-id="f60be-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="f60be-105">Celem tego nagrania jest przeprowadzenie użytkownika przez hierarchię wymiarów, tak aby mógł on kontynuować pracę do czasu utworzenia całej struktury raportowania w organizacji.</span><span class="sxs-lookup"><span data-stu-id="f60be-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="f60be-106">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="f60be-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="f60be-107">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="f60be-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="f60be-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-108">Click New.</span></span>
3. <span data-ttu-id="f60be-109">W polu HierarchyTypeComboBox wybierz opcję „Hierarchia klasyfikacji wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="f60be-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="f60be-110">Wybierz opcję Hierarchia klasyfikacji wymiarów.</span><span class="sxs-lookup"><span data-stu-id="f60be-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="f60be-111">Typ Hierarchia klasyfikacji wymiarów jest używany do definiowania reguł i na potrzeby sprawozdawczości.</span><span class="sxs-lookup"><span data-stu-id="f60be-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="f60be-112">Obsługuje wszystkie wymiary, takie jak obiekty kosztów, składniki kosztów i wymiary statystyczne.</span><span class="sxs-lookup"><span data-stu-id="f60be-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="f60be-113">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="f60be-113">Click Create.</span></span>
5. <span data-ttu-id="f60be-114">W polu Nazwa hierarchii wymiarów wpisz wartość „Organizacja USP2”.</span><span class="sxs-lookup"><span data-stu-id="f60be-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="f60be-115">W polu Wymiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f60be-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="f60be-116">Wybierz opcję Centra kosztów.</span><span class="sxs-lookup"><span data-stu-id="f60be-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="f60be-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-117">Click Save.</span></span>
8. <span data-ttu-id="f60be-118">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="f60be-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="f60be-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-119">Click New.</span></span>
10. <span data-ttu-id="f60be-120">W polu Nazwa węzła wpisz „Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="f60be-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="f60be-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-121">Click Save.</span></span>
12. <span data-ttu-id="f60be-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-122">Click New.</span></span>
13. <span data-ttu-id="f60be-123">W polu Nazwa węzła wpisz „Dyrektor generalny Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="f60be-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="f60be-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-124">Click Save.</span></span>
15. <span data-ttu-id="f60be-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-125">Click New.</span></span>
16. <span data-ttu-id="f60be-126">W polu Nazwa węzła wpisz „Region Wschód”.</span><span class="sxs-lookup"><span data-stu-id="f60be-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="f60be-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-127">Click Save.</span></span>
18. <span data-ttu-id="f60be-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-128">Click New.</span></span>
19. <span data-ttu-id="f60be-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f60be-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="f60be-130">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f60be-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f60be-131">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="f60be-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="f60be-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-132">Click Save.</span></span>
22. <span data-ttu-id="f60be-133">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny\Dyrektor generalny Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="f60be-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="f60be-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-134">Click New.</span></span>
24. <span data-ttu-id="f60be-135">W polu Nazwa węzła wpisz „Region Zachód”.</span><span class="sxs-lookup"><span data-stu-id="f60be-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="f60be-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-136">Click Save.</span></span>
26. <span data-ttu-id="f60be-137">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-137">Click New.</span></span>
27. <span data-ttu-id="f60be-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f60be-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="f60be-139">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f60be-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f60be-140">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="f60be-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="f60be-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-141">Click Save.</span></span>
30. <span data-ttu-id="f60be-142">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="f60be-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="f60be-143">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-143">Click New.</span></span>
32. <span data-ttu-id="f60be-144">W polu Nazwa węzła wpisz „Dyrektor finansowy Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="f60be-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="f60be-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-145">Click Save.</span></span>
34. <span data-ttu-id="f60be-146">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-146">Click New.</span></span>
35. <span data-ttu-id="f60be-147">W polu Nazwa węzła wpisz „Kampania marketingowa”.</span><span class="sxs-lookup"><span data-stu-id="f60be-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="f60be-148">W polu Nazwa węzła wpisz „Kampania marketingowa”.</span><span class="sxs-lookup"><span data-stu-id="f60be-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="f60be-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-149">Click Save.</span></span>
38. <span data-ttu-id="f60be-150">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-150">Click New.</span></span>
39. <span data-ttu-id="f60be-151">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f60be-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="f60be-152">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f60be-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f60be-153">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="f60be-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="f60be-154">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-154">Click Save.</span></span>
42. <span data-ttu-id="f60be-155">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny\Dyrektor finansowy Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="f60be-155">In the tree, select 'Oganization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="f60be-156">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-156">Click New.</span></span>
44. <span data-ttu-id="f60be-157">W polu Nazwa węzła wpisz „Targi”.</span><span class="sxs-lookup"><span data-stu-id="f60be-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="f60be-158">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-158">Click Save.</span></span>
46. <span data-ttu-id="f60be-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-159">Click New.</span></span>
47. <span data-ttu-id="f60be-160">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f60be-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="f60be-161">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f60be-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f60be-162">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="f60be-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="f60be-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-163">Click Save.</span></span>
50. <span data-ttu-id="f60be-164">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="f60be-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="f60be-165">W polu Nazwa węzła wpisz „Dyrektor ds. informatyki Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="f60be-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="f60be-166">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-166">Click Save.</span></span>
53. <span data-ttu-id="f60be-167">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-167">Click New.</span></span>
54. <span data-ttu-id="f60be-168">W polu Nazwa węzła wpisz „Biura obsługi”.</span><span class="sxs-lookup"><span data-stu-id="f60be-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="f60be-169">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-169">Click Save.</span></span>
56. <span data-ttu-id="f60be-170">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="f60be-170">Click New.</span></span>
57. <span data-ttu-id="f60be-171">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="f60be-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="f60be-172">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="f60be-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="f60be-173">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="f60be-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="f60be-174">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="f60be-174">Click Save.</span></span>


