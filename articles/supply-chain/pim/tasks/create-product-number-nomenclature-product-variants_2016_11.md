--- 
title: "Tworzenie numeru produktu dla skonfigurowanych wariantów produktu"
description: "Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym."
author: BibiSp
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4f1ae1e447813ac6d6514314fedb03b2d40d75a2
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-product-number-for-configured-product-variants"></a><span data-ttu-id="c4c93-103">Tworzenie numeru produktu dla skonfigurowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="c4c93-103">Create a product number for configured product variants</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c4c93-104">Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym.</span><span class="sxs-lookup"><span data-stu-id="c4c93-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="c4c93-105">W procedurze zademonstrowano również, jak zbudować konwencję nazewnictwa konfiguracji dla składnika modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="c4c93-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c4c93-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c4c93-107">Nowa konwencja nazewnictwa numerów produktu jest przypisana do produktu głównego D0004.</span><span class="sxs-lookup"><span data-stu-id="c4c93-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="c4c93-108">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="c4c93-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="c4c93-109">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="c4c93-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="c4c93-110">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="c4c93-111">Kliknij opcję Nazewnictwo produktów.</span><span class="sxs-lookup"><span data-stu-id="c4c93-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="c4c93-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c4c93-112">Click New.</span></span>
4. <span data-ttu-id="c4c93-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c4c93-114">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c4c93-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c4c93-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-115">Click Add.</span></span>
7. <span data-ttu-id="c4c93-116">Kliknij opcję Numer produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="c4c93-116">Click Product master number.</span></span>
8. <span data-ttu-id="c4c93-117">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-117">Click Add.</span></span>
9. <span data-ttu-id="c4c93-118">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c4c93-118">Click Text constant.</span></span>
10. <span data-ttu-id="c4c93-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="c4c93-120">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="c4c93-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-121">Click Add.</span></span>
13. <span data-ttu-id="c4c93-122">Kliknij opcję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="c4c93-122">Click Configuration.</span></span>
14. <span data-ttu-id="c4c93-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c93-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="c4c93-124">Przypisywanie konwencji nazewnictwa numerów produktu do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="c4c93-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="c4c93-125">Kliknij opcję Produkty główne.</span><span class="sxs-lookup"><span data-stu-id="c4c93-125">Click Product masters.</span></span>
2. <span data-ttu-id="c4c93-126">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="c4c93-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c4c93-127">Na przykład wyfiltruj według pola Numer produktu z wartością „D”.</span><span class="sxs-lookup"><span data-stu-id="c4c93-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="c4c93-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c4c93-129">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-129">Click Edit.</span></span>
5. <span data-ttu-id="c4c93-130">W polu Użyj nazewnictwa zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c4c93-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="c4c93-131">W polu Nazewnictwo numerów wariantów produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="c4c93-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c93-132">Close the page.</span></span>
8. <span data-ttu-id="c4c93-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c93-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="c4c93-134">Tworzenie konwencji nazewnictwa dla składnika modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="c4c93-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="c4c93-135">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="c4c93-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c4c93-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c4c93-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c4c93-138">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-138">Click Edit.</span></span>
5. <span data-ttu-id="c4c93-139">W polu Użyj nazewnictwa konfiguracji zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="c4c93-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="c4c93-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-140">Click Add.</span></span>
7. <span data-ttu-id="c4c93-141">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-141">Click Attribute value.</span></span>
8. <span data-ttu-id="c4c93-142">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="c4c93-143">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="c4c93-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="c4c93-144">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-144">Click Add.</span></span>
11. <span data-ttu-id="c4c93-145">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c4c93-145">Click Text constant.</span></span>
12. <span data-ttu-id="c4c93-146">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="c4c93-147">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="c4c93-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-148">Click Add.</span></span>
15. <span data-ttu-id="c4c93-149">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-149">Click Attribute value.</span></span>
16. <span data-ttu-id="c4c93-150">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="c4c93-151">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="c4c93-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="c4c93-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-152">Click Add.</span></span>
19. <span data-ttu-id="c4c93-153">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c4c93-153">Click Text constant.</span></span>
20. <span data-ttu-id="c4c93-154">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="c4c93-155">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="c4c93-156">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-156">Click Add.</span></span>
23. <span data-ttu-id="c4c93-157">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-157">Click Attribute value.</span></span>
24. <span data-ttu-id="c4c93-158">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="c4c93-159">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="c4c93-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="c4c93-160">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-160">Click Add.</span></span>
27. <span data-ttu-id="c4c93-161">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c4c93-161">Click Text constant.</span></span>
28. <span data-ttu-id="c4c93-162">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="c4c93-163">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="c4c93-164">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-164">Click Add.</span></span>
31. <span data-ttu-id="c4c93-165">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c4c93-165">Click Attribute value.</span></span>
32. <span data-ttu-id="c4c93-166">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="c4c93-167">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="c4c93-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="c4c93-168">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-168">Click Add.</span></span>
35. <span data-ttu-id="c4c93-169">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="c4c93-169">Click Text constant.</span></span>
36. <span data-ttu-id="c4c93-170">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="c4c93-171">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="c4c93-172">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="c4c93-172">Click Add.</span></span>
39. <span data-ttu-id="c4c93-173">Kliknij opcję Wartość sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="c4c93-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="c4c93-174">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c4c93-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="c4c93-175">W polu Sekwencja numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4c93-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="c4c93-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c93-176">Close the page.</span></span>
43. <span data-ttu-id="c4c93-177">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c93-177">Close the page.</span></span>
44. <span data-ttu-id="c4c93-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c4c93-178">Close the page.</span></span>


