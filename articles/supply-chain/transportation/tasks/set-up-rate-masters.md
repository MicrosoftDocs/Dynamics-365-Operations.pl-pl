---
title: Ustawianie danych głównych stawki
description: W tej procedurze pokazano sposób konfigurowania danych głównych stawki.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 44eb817bbc6053eeefaef18f9d3be1822bcb057c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981904"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="8fbca-103">Ustawianie danych głównych stawki</span><span class="sxs-lookup"><span data-stu-id="8fbca-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8fbca-104">W tej procedurze pokazano sposób konfigurowania danych głównych stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="8fbca-105">Zwykle dane główne stawek konfiguruje menedżer logistyki, w zależności od umów podpisanych z przewoźnikami.</span><span class="sxs-lookup"><span data-stu-id="8fbca-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="8fbca-106">W tym scenariuszu Ty skonfigurujesz dane główne stawki dla przewoźnika lotniczego.</span><span class="sxs-lookup"><span data-stu-id="8fbca-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="8fbca-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="8fbca-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="8fbca-108">Konfigurowanie danych głównych stawki</span><span class="sxs-lookup"><span data-stu-id="8fbca-108">Set up rate master</span></span>
1. <span data-ttu-id="8fbca-109">Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główna stawka.</span><span class="sxs-lookup"><span data-stu-id="8fbca-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="8fbca-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8fbca-110">Click New.</span></span>
3. <span data-ttu-id="8fbca-111">W polu Główna stawka wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8fbca-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="8fbca-112">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8fbca-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8fbca-113">W polu Identyfikator metadanych oceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8fbca-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8fbca-114">Identyfikator metadanych stawek określa informacje potrzebne w danych głównych stawki. Definiuje metadane oczekiwane przez aparat TMS używający tych danych głównych stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="8fbca-115">W tym przykładzie wybierz opcję P2P.</span><span class="sxs-lookup"><span data-stu-id="8fbca-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="8fbca-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8fbca-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8fbca-117">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8fbca-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="8fbca-118">Konfigurowanie podstawy stawki</span><span class="sxs-lookup"><span data-stu-id="8fbca-118">Set up rate base</span></span>
1. <span data-ttu-id="8fbca-119">Kliknij opcję Podstawa stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-119">Click Rate base.</span></span>
    * <span data-ttu-id="8fbca-120">Podstawa stawki decyduje o stawce przewoźnika i może służyć do konfigurowania struktury taryf, ponieważ określa strukturę stawek w punktach przerwania zdefiniowanych w danych głównych podziału.</span><span class="sxs-lookup"><span data-stu-id="8fbca-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="8fbca-121">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8fbca-121">Click New.</span></span>
3. <span data-ttu-id="8fbca-122">W polu Podstawa stawki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8fbca-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="8fbca-123">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8fbca-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8fbca-124">W polu Główna przerwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8fbca-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8fbca-125">Dane główne podziałów służą do definiowania struktury cen i jej punktów przerwania.</span><span class="sxs-lookup"><span data-stu-id="8fbca-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="8fbca-126">Struktura cen używa cen warstwowych opartych na wymiarach fizycznych.</span><span class="sxs-lookup"><span data-stu-id="8fbca-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="8fbca-127">W tym przykładzie użyj masy.</span><span class="sxs-lookup"><span data-stu-id="8fbca-127">For this example, use weight</span></span>
7. <span data-ttu-id="8fbca-128">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8fbca-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8fbca-129">Przełącz rozwinięcie sekcji Szczegóły.</span><span class="sxs-lookup"><span data-stu-id="8fbca-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="8fbca-130">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8fbca-130">Click New.</span></span>
10. <span data-ttu-id="8fbca-131">W polu Kod pocztowy dostawy wpisz „30301”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="8fbca-132">W polu Kod pocztowy celu dostawy wpisz „30318”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="8fbca-133">W polu Kraj/region dostawy wpisz „Stany Zjednoczone”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="8fbca-134">W polu <1,00 kg wpisz „100”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="8fbca-135">Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 1 kilogram.</span><span class="sxs-lookup"><span data-stu-id="8fbca-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="8fbca-136">W polu <5,00 kg wpisz „300”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="8fbca-137">Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 5 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="8fbca-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="8fbca-138">W polu <20,00 kg wpisz „500”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="8fbca-139">Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 20 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="8fbca-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="8fbca-140">W polu <100,00 kg wpisz „1000”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="8fbca-141">Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 100 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="8fbca-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="8fbca-142">W polu <1.000,00 kg wpisz „3000”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="8fbca-143">Wstaw stawkę za kg, jeśli łączna masa ładunku jest mniejsza niż 1000 kilogramów.</span><span class="sxs-lookup"><span data-stu-id="8fbca-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="8fbca-144">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8fbca-144">Click Save.</span></span>
19. <span data-ttu-id="8fbca-145">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="8fbca-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="8fbca-146">Przypisywanie podstawy stawki</span><span class="sxs-lookup"><span data-stu-id="8fbca-146">Assign rate base</span></span>
1. <span data-ttu-id="8fbca-147">Przełącz rozwinięcie sekcji Przypisania podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="8fbca-148">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="8fbca-148">Click New.</span></span>
    * <span data-ttu-id="8fbca-149">Dla każdych danych głównych stawki może istnieć kilka przypisań podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="8fbca-150">Dzięki temu dla każdego przewoźnika można utworzyć kilka różnych cen bazowych w zależności od miejsca przeznaczenia, usług lub różnych podstaw stawek.</span><span class="sxs-lookup"><span data-stu-id="8fbca-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="8fbca-151">W tej procedurze utworzysz tylko jedno przypisanie podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="8fbca-152">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="8fbca-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8fbca-153">W polu Podstawa stawki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8fbca-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="8fbca-154">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8fbca-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8fbca-155">W polu Usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="8fbca-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8fbca-156">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="8fbca-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8fbca-157">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8fbca-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8fbca-158">W polu Kod pocztowy miejsca odbioru wpisz „98052”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="8fbca-159">Określ kod pocztowy źródła dostawy, dla którego ma obowiązywać to przypisanie podstawy stawki.</span><span class="sxs-lookup"><span data-stu-id="8fbca-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="8fbca-160">W polu Kraj/region odbioru wpisz „Stany Zjednoczone”.</span><span class="sxs-lookup"><span data-stu-id="8fbca-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="8fbca-161">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="8fbca-161">Click Save.</span></span>

