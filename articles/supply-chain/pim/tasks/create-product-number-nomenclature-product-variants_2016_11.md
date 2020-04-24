---
title: Tworzenie konwencji nazewnictwa identyfikatorów produktów dla skonfigurowanych wariantów produktu
description: Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6970b37594bc999f8f1ea112a6056f15faccc02c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213260"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="593c2-103">Tworzenie konwencji nazewnictwa identyfikatorów produktów dla skonfigurowanych wariantów produktu</span><span class="sxs-lookup"><span data-stu-id="593c2-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="593c2-104">Ta procedura pokazuje, jak skonfigurować konwencję nazewnictwa numerów produktu dla skonfigurowanych wariantów produktu i jak można ją połączyć z konfigurowalnym produktem głównym.</span><span class="sxs-lookup"><span data-stu-id="593c2-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="593c2-105">W procedurze zademonstrowano również, jak zbudować konwencję nazewnictwa konfiguracji dla składnika modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="593c2-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="593c2-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="593c2-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="593c2-107">Nowa konwencja nazewnictwa numerów produktu jest przypisana do produktu głównego D0004.</span><span class="sxs-lookup"><span data-stu-id="593c2-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="593c2-108">Zazwyczaj zadanie wykonuje projektant produktów.</span><span class="sxs-lookup"><span data-stu-id="593c2-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="593c2-109">Tworzenie konwencji nazewnictwa numerów produktu</span><span class="sxs-lookup"><span data-stu-id="593c2-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="593c2-110">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="593c2-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="593c2-111">Kliknij opcję Nazewnictwo produktów.</span><span class="sxs-lookup"><span data-stu-id="593c2-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="593c2-112">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="593c2-112">Click New.</span></span>
4. <span data-ttu-id="593c2-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="593c2-114">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="593c2-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="593c2-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-115">Click Add.</span></span>
7. <span data-ttu-id="593c2-116">Kliknij opcję Numer produktu głównego.</span><span class="sxs-lookup"><span data-stu-id="593c2-116">Click Product master number.</span></span>
8. <span data-ttu-id="593c2-117">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-117">Click Add.</span></span>
9. <span data-ttu-id="593c2-118">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="593c2-118">Click Text constant.</span></span>
10. <span data-ttu-id="593c2-119">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="593c2-120">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="593c2-121">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-121">Click Add.</span></span>
13. <span data-ttu-id="593c2-122">Kliknij opcję Konfiguracja.</span><span class="sxs-lookup"><span data-stu-id="593c2-122">Click Configuration.</span></span>
14. <span data-ttu-id="593c2-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="593c2-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="593c2-124">Przypisywanie konwencji nazewnictwa numerów produktu do produktu głównego</span><span class="sxs-lookup"><span data-stu-id="593c2-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="593c2-125">Kliknij opcję Produkty główne.</span><span class="sxs-lookup"><span data-stu-id="593c2-125">Click Product masters.</span></span>
2. <span data-ttu-id="593c2-126">Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy.</span><span class="sxs-lookup"><span data-stu-id="593c2-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="593c2-127">Na przykład wyfiltruj według pola Numer produktu z wartością „D”.</span><span class="sxs-lookup"><span data-stu-id="593c2-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="593c2-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="593c2-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="593c2-129">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="593c2-129">Click Edit.</span></span>
5. <span data-ttu-id="593c2-130">W polu Użyj nazewnictwa zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="593c2-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="593c2-131">W polu Nazewnictwo numerów wariantów produktu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="593c2-132">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="593c2-132">Close the page.</span></span>
8. <span data-ttu-id="593c2-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="593c2-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="593c2-134">Tworzenie konwencji nazewnictwa dla składnika modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="593c2-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="593c2-135">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="593c2-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="593c2-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="593c2-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="593c2-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="593c2-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="593c2-138">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="593c2-138">Click Edit.</span></span>
5. <span data-ttu-id="593c2-139">W polu Użyj nazewnictwa konfiguracji zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="593c2-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="593c2-140">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-140">Click Add.</span></span>
7. <span data-ttu-id="593c2-141">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="593c2-141">Click Attribute value.</span></span>
8. <span data-ttu-id="593c2-142">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="593c2-143">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="593c2-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="593c2-144">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-144">Click Add.</span></span>
11. <span data-ttu-id="593c2-145">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="593c2-145">Click Text constant.</span></span>
12. <span data-ttu-id="593c2-146">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="593c2-147">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="593c2-148">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-148">Click Add.</span></span>
15. <span data-ttu-id="593c2-149">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="593c2-149">Click Attribute value.</span></span>
16. <span data-ttu-id="593c2-150">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="593c2-151">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="593c2-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="593c2-152">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-152">Click Add.</span></span>
19. <span data-ttu-id="593c2-153">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="593c2-153">Click Text constant.</span></span>
20. <span data-ttu-id="593c2-154">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="593c2-155">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="593c2-156">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-156">Click Add.</span></span>
23. <span data-ttu-id="593c2-157">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="593c2-157">Click Attribute value.</span></span>
24. <span data-ttu-id="593c2-158">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="593c2-159">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="593c2-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="593c2-160">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-160">Click Add.</span></span>
27. <span data-ttu-id="593c2-161">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="593c2-161">Click Text constant.</span></span>
28. <span data-ttu-id="593c2-162">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="593c2-163">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="593c2-164">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-164">Click Add.</span></span>
31. <span data-ttu-id="593c2-165">Kliknij opcję Wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="593c2-165">Click Attribute value.</span></span>
32. <span data-ttu-id="593c2-166">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="593c2-167">Wprowadź lub wybierz wartość w polu Atrybut.</span><span class="sxs-lookup"><span data-stu-id="593c2-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="593c2-168">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-168">Click Add.</span></span>
35. <span data-ttu-id="593c2-169">Kliknij opcję Stała tekstowa.</span><span class="sxs-lookup"><span data-stu-id="593c2-169">Click Text constant.</span></span>
36. <span data-ttu-id="593c2-170">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="593c2-171">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="593c2-172">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="593c2-172">Click Add.</span></span>
39. <span data-ttu-id="593c2-173">Kliknij opcję Wartość sekwencji numerów.</span><span class="sxs-lookup"><span data-stu-id="593c2-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="593c2-174">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="593c2-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="593c2-175">W polu Sekwencja numerów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="593c2-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="593c2-176">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="593c2-176">Close the page.</span></span>
43. <span data-ttu-id="593c2-177">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="593c2-177">Close the page.</span></span>
44. <span data-ttu-id="593c2-178">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="593c2-178">Close the page.</span></span>

