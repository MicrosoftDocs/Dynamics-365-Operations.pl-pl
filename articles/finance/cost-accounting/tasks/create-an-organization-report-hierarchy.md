---
title: Tworzenie hierarchii organizacyjnej raportowania
description: Ta procedura służy do tworzenia hierarchii raportów dla sprawozdawczości w organizacji.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02c87d25db447c82fd00042a37c040c52fa366a9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144454"
---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="82a2c-103">Tworzenie hierarchii organizacyjnej raportowania</span><span class="sxs-lookup"><span data-stu-id="82a2c-103">Create an organization report hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82a2c-104">Ta procedura służy do tworzenia hierarchii raportów dla sprawozdawczości w organizacji.</span><span class="sxs-lookup"><span data-stu-id="82a2c-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="82a2c-105">Celem tego nagrania jest przeprowadzenie użytkownika przez hierarchię wymiarów, tak aby mógł on kontynuować pracę do czasu utworzenia całej struktury raportowania w organizacji.</span><span class="sxs-lookup"><span data-stu-id="82a2c-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="82a2c-106">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="82a2c-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="82a2c-107">Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.</span><span class="sxs-lookup"><span data-stu-id="82a2c-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="82a2c-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-108">Click New.</span></span>
3. <span data-ttu-id="82a2c-109">W polu HierarchyTypeComboBox wybierz opcję „Hierarchia klasyfikacji wymiarów”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="82a2c-110">Wybierz opcję Hierarchia klasyfikacji wymiarów.</span><span class="sxs-lookup"><span data-stu-id="82a2c-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="82a2c-111">Typ Hierarchia klasyfikacji wymiarów jest używany do definiowania reguł i na potrzeby sprawozdawczości.</span><span class="sxs-lookup"><span data-stu-id="82a2c-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="82a2c-112">Obsługuje wszystkie wymiary, takie jak obiekty kosztów, składniki kosztów i wymiary statystyczne.</span><span class="sxs-lookup"><span data-stu-id="82a2c-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="82a2c-113">Kliknij przycisk Utwórz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-113">Click Create.</span></span>
5. <span data-ttu-id="82a2c-114">W polu Nazwa hierarchii wymiarów wpisz wartość „Organizacja USP2”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="82a2c-115">W polu Wymiar wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="82a2c-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="82a2c-116">Wybierz opcję Centra kosztów.</span><span class="sxs-lookup"><span data-stu-id="82a2c-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="82a2c-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-117">Click Save.</span></span>
8. <span data-ttu-id="82a2c-118">Kliknij opcję Wyświetl hierarchię.</span><span class="sxs-lookup"><span data-stu-id="82a2c-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="82a2c-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-119">Click New.</span></span>
10. <span data-ttu-id="82a2c-120">W polu Nazwa węzła wpisz „Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="82a2c-121">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-121">Click Save.</span></span>
12. <span data-ttu-id="82a2c-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-122">Click New.</span></span>
13. <span data-ttu-id="82a2c-123">W polu Nazwa węzła wpisz „Dyrektor generalny Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="82a2c-124">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-124">Click Save.</span></span>
15. <span data-ttu-id="82a2c-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-125">Click New.</span></span>
16. <span data-ttu-id="82a2c-126">W polu Nazwa węzła wpisz „Region Wschód”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="82a2c-127">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-127">Click Save.</span></span>
18. <span data-ttu-id="82a2c-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-128">Click New.</span></span>
19. <span data-ttu-id="82a2c-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="82a2c-130">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="82a2c-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="82a2c-131">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="82a2c-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="82a2c-132">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-132">Click Save.</span></span>
22. <span data-ttu-id="82a2c-133">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny\Dyrektor generalny Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="82a2c-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-134">Click New.</span></span>
24. <span data-ttu-id="82a2c-135">W polu Nazwa węzła wpisz „Region Zachód”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="82a2c-136">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-136">Click Save.</span></span>
26. <span data-ttu-id="82a2c-137">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-137">Click New.</span></span>
27. <span data-ttu-id="82a2c-138">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="82a2c-139">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="82a2c-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="82a2c-140">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="82a2c-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="82a2c-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-141">Click Save.</span></span>
30. <span data-ttu-id="82a2c-142">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="82a2c-143">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-143">Click New.</span></span>
32. <span data-ttu-id="82a2c-144">W polu Nazwa węzła wpisz „Dyrektor finansowy Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="82a2c-145">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-145">Click Save.</span></span>
34. <span data-ttu-id="82a2c-146">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-146">Click New.</span></span>
35. <span data-ttu-id="82a2c-147">W polu Nazwa węzła wpisz „Kampania marketingowa”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="82a2c-148">W polu Nazwa węzła wpisz „Kampania marketingowa”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="82a2c-149">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-149">Click Save.</span></span>
38. <span data-ttu-id="82a2c-150">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-150">Click New.</span></span>
39. <span data-ttu-id="82a2c-151">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="82a2c-152">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="82a2c-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="82a2c-153">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="82a2c-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="82a2c-154">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-154">Click Save.</span></span>
42. <span data-ttu-id="82a2c-155">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny\Dyrektor finansowy Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="82a2c-156">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-156">Click New.</span></span>
44. <span data-ttu-id="82a2c-157">W polu Nazwa węzła wpisz „Targi”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="82a2c-158">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-158">Click Save.</span></span>
46. <span data-ttu-id="82a2c-159">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-159">Click New.</span></span>
47. <span data-ttu-id="82a2c-160">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="82a2c-161">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="82a2c-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="82a2c-162">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="82a2c-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="82a2c-163">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-163">Click Save.</span></span>
50. <span data-ttu-id="82a2c-164">W drzewie zaznacz element „Organizacja USP2\Dyrektor generalny”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="82a2c-165">W polu Nazwa węzła wpisz „Dyrektor ds. informatyki Centra kosztów”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="82a2c-166">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-166">Click Save.</span></span>
53. <span data-ttu-id="82a2c-167">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-167">Click New.</span></span>
54. <span data-ttu-id="82a2c-168">W polu Nazwa węzła wpisz „Biura obsługi”.</span><span class="sxs-lookup"><span data-stu-id="82a2c-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="82a2c-169">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-169">Click Save.</span></span>
56. <span data-ttu-id="82a2c-170">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="82a2c-170">Click New.</span></span>
57. <span data-ttu-id="82a2c-171">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="82a2c-172">W polu Element członkowskiego wymiaru źródłowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="82a2c-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="82a2c-173">Wybierz element członkowski wymiaru odpowiadający węzłowi.</span><span class="sxs-lookup"><span data-stu-id="82a2c-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="82a2c-174">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="82a2c-174">Click Save.</span></span>

