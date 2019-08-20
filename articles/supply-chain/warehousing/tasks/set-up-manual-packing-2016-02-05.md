---
title: Konfigurowanie pakowania ręcznego (luty 2016 i maj 2016)
description: Proces pakowania umożliwia sprawdzenie poprawności produktów i ich zapakowanie do kontenerów.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30bbb404e624c33e047c5505c5b21565ed8cce10
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847190"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="d3477-103">Konfigurowanie pakowania ręcznego (luty 2016 i maj 2016)</span><span class="sxs-lookup"><span data-stu-id="d3477-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d3477-104">Proces pakowania umożliwia sprawdzenie poprawności produktów i ich zapakowanie do kontenerów.</span><span class="sxs-lookup"><span data-stu-id="d3477-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="d3477-105">W tym procesie pracownicy magazynu pobierają produkty z lokalizacji przechowywania i przenoszą je do stacji pakowania, gdzie sprawdzają typy i ilości towarów oraz przypisują je do odpowiednich kontenerów.</span><span class="sxs-lookup"><span data-stu-id="d3477-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="d3477-106">Jeśli kontener jest całkowicie zapakowany, pracownicy mogą go zamknąć i przenieść do doków załadunkowych, skąd produkty są gotowe do wysyłki.</span><span class="sxs-lookup"><span data-stu-id="d3477-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="d3477-107">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="d3477-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="d3477-108">Ta procedura dotyczy tylko programu Dynamics 365 for Operations w wersjach z lutego i maja 2016 roku.</span><span class="sxs-lookup"><span data-stu-id="d3477-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="d3477-109">Ustaw profile lokalizacji</span><span class="sxs-lookup"><span data-stu-id="d3477-109">Set up location profiles</span></span>
1. <span data-ttu-id="d3477-110">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Magazyn > Profile lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="d3477-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="d3477-111">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d3477-111">Click New.</span></span>
    * <span data-ttu-id="d3477-112">Profil lokalizacji jest używany w stacjach pakowania. Zawiera informacje i reguły dotyczące lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="d3477-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="d3477-113">W polu Identyfikator profilu lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="d3477-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d3477-115">W polu Format lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="d3477-116">W polu Typ lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="d3477-117">W polu Pozwól na mieszane pozycje wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="d3477-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="d3477-118">W polu Pozwól na mieszane stany zapasów wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="d3477-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="d3477-119">W polu Zastąp reguły dla dni partii wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="d3477-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="d3477-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3477-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="d3477-121">Konfigurowanie parametrów zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="d3477-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="d3477-122">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="d3477-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="d3477-123">Kliknij kartę Opakowanie.</span><span class="sxs-lookup"><span data-stu-id="d3477-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="d3477-124">W polu Identyfikator profilu lokalizacji pakowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="d3477-125">Zaznacz profil lokalizacji, którego chcesz używać do pakowania.</span><span class="sxs-lookup"><span data-stu-id="d3477-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="d3477-126">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3477-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="d3477-127">Konfigurowanie typów kontenerów</span><span class="sxs-lookup"><span data-stu-id="d3477-127">Set up container types</span></span>
1. <span data-ttu-id="d3477-128">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Typy kontenerów.</span><span class="sxs-lookup"><span data-stu-id="d3477-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="d3477-129">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d3477-129">Click New.</span></span>
    * <span data-ttu-id="d3477-130">Można zdefiniować typy kontenerów, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="d3477-130">You can define the types of containers to use.</span></span> <span data-ttu-id="d3477-131">Można określić wymiary fizyczne kontenera, w tym tarę, maksymalną wagę, maksymalną objętość, długość, szerokość i wagę.</span><span class="sxs-lookup"><span data-stu-id="d3477-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="d3477-132">Atrybuty są konfigurowalnymi polami, które umożliwiają dodawanie kolejnych wymiarów do typu kontenera.</span><span class="sxs-lookup"><span data-stu-id="d3477-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="d3477-133">W polu Kod typu kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="d3477-134">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="d3477-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d3477-135">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d3477-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="d3477-136">W polu Maksymalna waga wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d3477-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="d3477-137">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d3477-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="d3477-138">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="d3477-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="d3477-139">W polu Szerokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d3477-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="d3477-140">W polu Wysokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="d3477-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="d3477-141">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d3477-141">Click Save.</span></span>
12. <span data-ttu-id="d3477-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3477-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="d3477-143">Konfigurowanie profili pakowania</span><span class="sxs-lookup"><span data-stu-id="d3477-143">Set up packing profiles</span></span>
1. <span data-ttu-id="d3477-144">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Opakowanie > Profile pakowania.</span><span class="sxs-lookup"><span data-stu-id="d3477-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="d3477-145">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d3477-145">Click New.</span></span>
3. <span data-ttu-id="d3477-146">W polu Identyfikator profilu pakowania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="d3477-147">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="d3477-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d3477-148">W polu Identyfikator profilu zamknięcia kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="d3477-149">Identyfikator profilu zamknięcia kontenera jest opcjonalny i pełni rolę domyślnego profilu zamknięcia kontenera dla tego profilu opakowania.</span><span class="sxs-lookup"><span data-stu-id="d3477-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="d3477-150">W polu Tryb identyfikatora kontenera wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d3477-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="d3477-151">Ta opcja decyduje, czy identyfikator kontenera będzie automatycznie generowany podczas tworzenia kontenera czy też będzie generowany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="d3477-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="d3477-152">W polu Typ kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="d3477-153">Typ kontenera będzie używany domyślnie podczas tworzenia nowego kontenera.</span><span class="sxs-lookup"><span data-stu-id="d3477-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="d3477-154">Zaznacz pole wyboru Automatycznie twórz kontener podczas zamykania kontenera.</span><span class="sxs-lookup"><span data-stu-id="d3477-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="d3477-155">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d3477-155">Click Save.</span></span>
10. <span data-ttu-id="d3477-156">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3477-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="d3477-157">Konfigurowanie profili zamknięcia kontenera</span><span class="sxs-lookup"><span data-stu-id="d3477-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="d3477-158">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Profile zamknięcia kontenera.</span><span class="sxs-lookup"><span data-stu-id="d3477-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="d3477-159">Profile zamknięcia kontenera określają, co się dzieje podczas zamykania kontenera.</span><span class="sxs-lookup"><span data-stu-id="d3477-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="d3477-160">Można skonfigurować wiele profili zamknięcia kontenera.</span><span class="sxs-lookup"><span data-stu-id="d3477-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="d3477-161">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d3477-161">Click New.</span></span>
3. <span data-ttu-id="d3477-162">W polu Identyfikator profilu zamknięcia kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="d3477-163">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="d3477-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d3477-164">W polu Manifest wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d3477-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="d3477-165">Umożliwia określenie, czy generowanie manifestu będzie następowało podczas zamykania kontenerów czy podczas potwierdzania wysyłki.</span><span class="sxs-lookup"><span data-stu-id="d3477-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="d3477-166">Należy zwrócić uwagę, że funkcja tworzenia manifestów wymaga obecności funkcji zarządzania transportem.</span><span class="sxs-lookup"><span data-stu-id="d3477-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="d3477-167">Aby tworzenie manifestów działało, musi być zaimplementowane w aparatach transportu.</span><span class="sxs-lookup"><span data-stu-id="d3477-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="d3477-168">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="d3477-169">W polu Domyślna lokalizacja końcowej wysyłki wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="d3477-170">Będzie to lokalizacja, do której będą przenoszone produkty po zamknięciu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="d3477-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="d3477-171">Ta lokalizacja musi mieć zdefiniowany profil lokalizacji w parametrach magazynu.</span><span class="sxs-lookup"><span data-stu-id="d3477-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="d3477-172">W polu Jednostka wagi wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3477-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="d3477-173">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d3477-173">Click Save.</span></span>

