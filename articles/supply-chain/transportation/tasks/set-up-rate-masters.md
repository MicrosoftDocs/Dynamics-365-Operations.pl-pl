---
title: Ustawianie danych głównych stawki
description: W tej procedurze pokazano sposób konfigurowania danych głównych stawki.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47fa7edeba81d826a00668a2da74113f552437f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974267"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="0ebbb-103">Ustawianie danych głównych stawki</span><span class="sxs-lookup"><span data-stu-id="0ebbb-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ebbb-104">W tej procedurze pokazano sposób konfigurowania danych głównych stawki.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="0ebbb-105">Zwykle dane główne stawek konfiguruje menedżer logistyki, w zależności od umów podpisanych z przewoźnikami.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="0ebbb-106">W tym scenariuszu Ty skonfigurujesz dane główne stawki dla przewoźnika lotniczego.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="0ebbb-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="0ebbb-108">Ustawianie głównej przerwy</span><span class="sxs-lookup"><span data-stu-id="0ebbb-108">Set up break master</span></span>

1. <span data-ttu-id="0ebbb-109">Wybierz kolejno opcje **Zarządzanie transportem > Ustawienia > Ocena > Główna przerwa**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="0ebbb-110">Dane główne podziałów służą do definiowania struktury cen i jej punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="0ebbb-111">Struktura cen używa cen warstwowych opartych na wymiarach fizycznych.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="0ebbb-112">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-112">Select **New**.</span></span>
1. <span data-ttu-id="0ebbb-113">W polu **Główna przerwa** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="0ebbb-114">Wprowadź wartość w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="0ebbb-115">W polu **Typ danych** wybierz typ danych.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="0ebbb-116">W polu **Porównanie** wprowadź żądany rodzaj porównania (za pomocą operatorów).</span><span class="sxs-lookup"><span data-stu-id="0ebbb-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="0ebbb-117">Wprowadź wartości jednostek przerwy w polu **Jednostka przerwy**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="0ebbb-118">W sekcji **Szczegóły** utwórz tyle przerw, ile jest potrzebnych dla struktury cenowej.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="0ebbb-119">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="0ebbb-120">Konfigurowanie danych głównych stawki</span><span class="sxs-lookup"><span data-stu-id="0ebbb-120">Set up rate master</span></span>

1. <span data-ttu-id="0ebbb-121">Wybierz kolejno opcje **Zarządzanie transportem > Ustawienia > Ocena > Główna stawka**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="0ebbb-122">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-122">Select **New**.</span></span>
1. <span data-ttu-id="0ebbb-123">W polu **Główna stawka** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="0ebbb-124">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="0ebbb-125">W polu **Identyfikator metadanych oceny** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="0ebbb-126">Identyfikator metadanych stawek określa informacje potrzebne w danych głównych stawki. Definiuje metadane oczekiwane przez aparat zarządzania transportem używający tych danych głównych stawki.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="0ebbb-127">W tym przykładzie wybierz opcję P2P.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-127">For this example, select the P2P option.</span></span> <span data-ttu-id="0ebbb-128">Jest już zdefiniowany w danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="0ebbb-129">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="0ebbb-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="0ebbb-131">Konfigurowanie podstawy stawki</span><span class="sxs-lookup"><span data-stu-id="0ebbb-131">Set up rate base</span></span>

1. <span data-ttu-id="0ebbb-132">Wybierz **Podstawa stawki**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="0ebbb-133">Podstawa stawki decyduje o stawce przewoźnika i może służyć do konfigurowania struktury taryf, ponieważ określa strukturę stawek w punktach przerwania zdefiniowanych w danych głównych podziału.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="0ebbb-134">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-134">Select **New**.</span></span>
3. <span data-ttu-id="0ebbb-135">W polu **Podstawa stawki** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="0ebbb-136">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="0ebbb-137">W polu **Główna przerwa** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0ebbb-138">Dane główne podziałów służą do definiowania struktury cen i jej punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="0ebbb-139">Struktura cen używa cen warstwowych opartych na wymiarach fizycznych.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="0ebbb-140">W tym przykładzie użyj masy.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-140">For this example, use weight.</span></span> <span data-ttu-id="0ebbb-141">Jest już zdefiniowany w danych demonstracyjnych.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="0ebbb-142">Na liście wybierz łącze w podkreślonym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="0ebbb-143">Rozwiń sekcję **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="0ebbb-144">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-144">Select **New**.</span></span>
10. <span data-ttu-id="0ebbb-145">W polu **Kod pocztowy dostawy** wpisz „30301”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="0ebbb-146">W polu **Kod pocztowy celu dostawy** wpisz „30318”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="0ebbb-147">W polu **Kraj/region dostawy** wpisz „Stany Zjednoczone”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="0ebbb-148">W polu **<1,00 kg** wpisz „100”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="0ebbb-149">Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 1 kilogram.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="0ebbb-150">W polu **<5,00 kg** wpisz „300”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="0ebbb-151">Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 5 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="0ebbb-152">W polu **<20,00 kg** wpisz „500”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="0ebbb-153">Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 20 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="0ebbb-154">W polu **<100,00 kg** wpisz „1000”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="0ebbb-155">Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 100 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="0ebbb-156">W polu **<1.000,00 kg** wpisz „3000”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="0ebbb-157">Wstaw stawkę za kilogram, jeśli łączna masa ładunku jest mniejsza niż 1000 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="0ebbb-158">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-158">Select **Save**.</span></span>
19. <span data-ttu-id="0ebbb-159">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="0ebbb-160">Przypisywanie podstawy stawki</span><span class="sxs-lookup"><span data-stu-id="0ebbb-160">Assign rate base</span></span>

1. <span data-ttu-id="0ebbb-161">Rozwiń lub zwiń sekcję **Przypisania podstawy stawki**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="0ebbb-162">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-162">Select **New**.</span></span>
    * <span data-ttu-id="0ebbb-163">Dla każdych danych głównych stawki może istnieć kilka przypisań podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="0ebbb-164">Dzięki temu dla każdego przewoźnika można utworzyć kilka różnych cen bazowych w zależności od miejsca przeznaczenia, usług lub różnych podstaw stawek.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="0ebbb-165">W tej procedurze utworzysz tylko jedno przypisanie podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="0ebbb-166">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="0ebbb-167">W polu **Podstawa stawki** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="0ebbb-168">Na liście wybierz łącze w podkreślonym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="0ebbb-169">W polu **Usługa** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="0ebbb-170">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="0ebbb-171">Na liście wybierz łącze w podkreślonym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="0ebbb-172">W polu **Kod pocztowy miejsca odbioru** wpisz „98052”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="0ebbb-173">Określ kod pocztowy źródła dostawy, dla którego ma obowiązywać to przypisanie podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="0ebbb-174">W polu **Kraj/region odbioru** wpisz „Stany Zjednoczone”.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="0ebbb-175">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0ebbb-175">Select **Save**.</span></span>
