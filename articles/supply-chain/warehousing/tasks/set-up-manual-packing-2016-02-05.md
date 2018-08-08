--- 
title: "Konfigurowanie pakowania ręcznego (tylko luty i maj 2016)"
description: "Proces pakowania umożliwia sprawdzenie poprawności produktów i ich zapakowanie do kontenerów."
author: ShylaThompson
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 7e776a08ec2adc48b77c86c16e1f291e524a8d00
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="61998-103">Konfigurowanie pakowania ręcznego (tylko luty i maj 2016)</span><span class="sxs-lookup"><span data-stu-id="61998-103">Set up manual packing (February & May 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="61998-104">Proces pakowania umożliwia sprawdzenie poprawności produktów i ich zapakowanie do kontenerów.</span><span class="sxs-lookup"><span data-stu-id="61998-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="61998-105">W tym procesie pracownicy magazynu pobierają produkty z lokalizacji przechowywania i przenoszą je do stacji pakowania, gdzie sprawdzają typy i ilości towarów oraz przypisują je do odpowiednich kontenerów.</span><span class="sxs-lookup"><span data-stu-id="61998-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="61998-106">Jeśli kontener jest całkowicie zapakowany, pracownicy mogą go zamknąć i przenieść do doków załadunkowych, skąd produkty są gotowe do wysyłki.</span><span class="sxs-lookup"><span data-stu-id="61998-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="61998-107">Ta procedura wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="61998-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="61998-108">Ustaw profile lokalizacji</span><span class="sxs-lookup"><span data-stu-id="61998-108">Set up location profiles</span></span>
1. <span data-ttu-id="61998-109">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Magazyn > Profile lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="61998-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="61998-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="61998-110">Click New.</span></span>
    * <span data-ttu-id="61998-111">Profil lokalizacji jest używany w stacjach pakowania. Zawiera informacje i reguły dotyczące lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="61998-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="61998-112">W polu Identyfikator profilu lokalizacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="61998-113">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="61998-114">W polu Format lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="61998-115">W polu Typ lokalizacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="61998-116">W polu Pozwól na mieszane pozycje wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="61998-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="61998-117">W polu Pozwól na mieszane stany zapasów wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="61998-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="61998-118">W polu Zastąp reguły dla dni partii wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="61998-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="61998-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61998-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="61998-120">Konfigurowanie parametrów zarządzania magazynem</span><span class="sxs-lookup"><span data-stu-id="61998-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="61998-121">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem.</span><span class="sxs-lookup"><span data-stu-id="61998-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="61998-122">Kliknij kartę Opakowanie.</span><span class="sxs-lookup"><span data-stu-id="61998-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="61998-123">W polu Identyfikator profilu lokalizacji pakowania wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="61998-124">Zaznacz profil lokalizacji, którego chcesz używać do pakowania.</span><span class="sxs-lookup"><span data-stu-id="61998-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="61998-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61998-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="61998-126">Konfigurowanie typów kontenerów</span><span class="sxs-lookup"><span data-stu-id="61998-126">Set up container types</span></span>
1. <span data-ttu-id="61998-127">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Typy kontenerów.</span><span class="sxs-lookup"><span data-stu-id="61998-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="61998-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="61998-128">Click New.</span></span>
    * <span data-ttu-id="61998-129">Można zdefiniować typy kontenerów, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="61998-129">You can define the types of containers to use.</span></span> <span data-ttu-id="61998-130">Można określić wymiary fizyczne kontenera, w tym tarę, maksymalną wagę, maksymalną objętość, długość, szerokość i wagę.</span><span class="sxs-lookup"><span data-stu-id="61998-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="61998-131">Atrybuty są konfigurowalnymi polami, które umożliwiają dodawanie kolejnych wymiarów do typu kontenera.</span><span class="sxs-lookup"><span data-stu-id="61998-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="61998-132">W polu Kod typu kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="61998-133">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="61998-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="61998-134">W polu Waga tara wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="61998-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="61998-135">W polu Maksymalna waga wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="61998-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="61998-136">W polu Objętość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="61998-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="61998-137">W polu Długość wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="61998-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="61998-138">W polu Szerokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="61998-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="61998-139">W polu Wysokość wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="61998-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="61998-140">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="61998-140">Click Save.</span></span>
12. <span data-ttu-id="61998-141">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61998-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="61998-142">Konfigurowanie profili pakowania</span><span class="sxs-lookup"><span data-stu-id="61998-142">Set up packing profiles</span></span>
1. <span data-ttu-id="61998-143">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Opakowanie > Profile pakowania.</span><span class="sxs-lookup"><span data-stu-id="61998-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="61998-144">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="61998-144">Click New.</span></span>
3. <span data-ttu-id="61998-145">W polu Identyfikator profilu pakowania wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="61998-146">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="61998-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="61998-147">W polu Identyfikator profilu zamknięcia kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="61998-148">Identyfikator profilu zamknięcia kontenera jest opcjonalny i pełni rolę domyślnego profilu zamknięcia kontenera dla tego profilu opakowania.</span><span class="sxs-lookup"><span data-stu-id="61998-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="61998-149">W polu Tryb identyfikatora kontenera wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="61998-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="61998-150">Ta opcja decyduje, czy identyfikator kontenera będzie automatycznie generowany podczas tworzenia kontenera czy też będzie generowany ręcznie.</span><span class="sxs-lookup"><span data-stu-id="61998-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="61998-151">W polu Typ kontenera wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="61998-152">Typ kontenera będzie używany domyślnie podczas tworzenia nowego kontenera.</span><span class="sxs-lookup"><span data-stu-id="61998-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="61998-153">Zaznacz pole wyboru Automatycznie twórz kontener podczas zamykania kontenera.</span><span class="sxs-lookup"><span data-stu-id="61998-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="61998-154">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="61998-154">Click Save.</span></span>
10. <span data-ttu-id="61998-155">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="61998-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="61998-156">Konfigurowanie profili zamknięcia kontenera</span><span class="sxs-lookup"><span data-stu-id="61998-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="61998-157">Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Profile zamknięcia kontenera.</span><span class="sxs-lookup"><span data-stu-id="61998-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="61998-158">Profile zamknięcia kontenera określają, co się dzieje podczas zamykania kontenera.</span><span class="sxs-lookup"><span data-stu-id="61998-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="61998-159">Można skonfigurować wiele profili zamknięcia kontenera.</span><span class="sxs-lookup"><span data-stu-id="61998-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="61998-160">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="61998-160">Click New.</span></span>
3. <span data-ttu-id="61998-161">W polu Identyfikator profilu zamknięcia kontenera wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="61998-162">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="61998-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="61998-163">W polu Manifest wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="61998-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="61998-164">Umożliwia określenie, czy generowanie manifestu będzie następowało podczas zamykania kontenerów czy podczas potwierdzania wysyłki.</span><span class="sxs-lookup"><span data-stu-id="61998-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="61998-165">Należy zwrócić uwagę, że funkcja tworzenia manifestów wymaga obecności funkcji zarządzania transportem.</span><span class="sxs-lookup"><span data-stu-id="61998-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="61998-166">Aby tworzenie manifestów działało, musi być zaimplementowane w aparatach transportu.</span><span class="sxs-lookup"><span data-stu-id="61998-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="61998-167">W polu Magazyn wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="61998-168">W polu Domyślna lokalizacja końcowej wysyłki wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="61998-169">Będzie to lokalizacja, do której będą przenoszone produkty po zamknięciu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="61998-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="61998-170">Ta lokalizacja musi mieć zdefiniowany profil lokalizacji w parametrach magazynu.</span><span class="sxs-lookup"><span data-stu-id="61998-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="61998-171">W polu Jednostka wagi wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="61998-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="61998-172">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="61998-172">Click Save.</span></span>


