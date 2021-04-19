---
title: Kontenery wysyłkowe
description: W tym temacie opisano, jak skonfigurować informacje o kontenerach wysyłkowych dla modułu Koszt z wyładunkiem.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2f7e9435aa3d0d06e1cc51457a6343b807d76dc7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833720"
---
# <a name="shipping-container-setup"></a><span data-ttu-id="301f2-103">Konfiguracja kontenera wysyłkowego</span><span class="sxs-lookup"><span data-stu-id="301f2-103">Shipping container setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="301f2-104">W tym temacie opisano, jak skonfigurować informacje o kontenerach wysyłkowych dla modułu **Koszt z wyładunkiem**.</span><span class="sxs-lookup"><span data-stu-id="301f2-104">This topic describes how to set up shipping containers for the **Landed cost** module.</span></span>

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a><span data-ttu-id="301f2-105">Konfigurowanie typów kontenerów wysyłkowych</span><span class="sxs-lookup"><span data-stu-id="301f2-105">Set up shipping container types</span></span>

<span data-ttu-id="301f2-106">Typy kontenerów wysyłkowych określają typy kontenerów wysyłkowych, które są dostępne do użycia podczas wysyłki i podróży.</span><span class="sxs-lookup"><span data-stu-id="301f2-106">Shipping container types define the types of shipping containers that are available for use during shipping and voyages.</span></span>

<span data-ttu-id="301f2-107">Aby pracować z typami kontenerów wysyłkowych, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Typy kontenerów wysyłkowych**.</span><span class="sxs-lookup"><span data-stu-id="301f2-107">To work with the shipping container types, go to **Landed cost \> Containers setup \> Shipping container types**.</span></span> <span data-ttu-id="301f2-108">Można tam wyświetlać, dodawać i usuwać rekordy typów kontenerów.</span><span class="sxs-lookup"><span data-stu-id="301f2-108">There, you can view, add, and remove records for your container types.</span></span> <span data-ttu-id="301f2-109">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="301f2-109">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="301f2-110">Pole</span><span class="sxs-lookup"><span data-stu-id="301f2-110">Field</span></span> | <span data-ttu-id="301f2-111">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-111">Description</span></span> |
|---|---|
| <span data-ttu-id="301f2-112">Typ kontenera wysyłkowego</span><span class="sxs-lookup"><span data-stu-id="301f2-112">Shipping container type</span></span> | <span data-ttu-id="301f2-113">Wprowadź unikalną nazwę/numer identyfikacyjny typu kontenera.</span><span class="sxs-lookup"><span data-stu-id="301f2-113">Enter a unique identification name/number for the shipping container type.</span></span> |
| <span data-ttu-id="301f2-114">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-114">Description</span></span> | <span data-ttu-id="301f2-115">Wprowadź opis typu kontenera wysyłkowego.</span><span class="sxs-lookup"><span data-stu-id="301f2-115">Enter a description of the shipping container type.</span></span> |
| <span data-ttu-id="301f2-116">Objętość</span><span class="sxs-lookup"><span data-stu-id="301f2-116">Volume</span></span> | <span data-ttu-id="301f2-117">Wprowadź maksymalną objętość dozwoloną w kontenerach transportowych tego typu.</span><span class="sxs-lookup"><span data-stu-id="301f2-117">Enter the maximum volume that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="301f2-118">Masa</span><span class="sxs-lookup"><span data-stu-id="301f2-118">Weight</span></span> | <span data-ttu-id="301f2-119">Wprowadź maksymalną wagę dozwoloną w kontenerach transportowych tego typu.</span><span class="sxs-lookup"><span data-stu-id="301f2-119">Enter the maximum weight that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="301f2-120">Z możliwością zwrotu</span><span class="sxs-lookup"><span data-stu-id="301f2-120">Returnable</span></span> | <span data-ttu-id="301f2-121">Określ, czy kontenery transportowe tego typu mogą zostać zwrócone dostawcy po ich wykorzystaniu podczas podróży.</span><span class="sxs-lookup"><span data-stu-id="301f2-121">Specify whether shipping containers of this type can be returned to the vendor after they are used during a voyage.</span></span> <span data-ttu-id="301f2-122">Jeśli ta opcja ma wartość *Tak*, w przypadku zwrotu kontenerów wysyłkowych tego typu do portu pochodzenia mogą być stosowane dodatkowe koszty.</span><span class="sxs-lookup"><span data-stu-id="301f2-122">If this option is set to *Yes*, additional costs might apply for the return of shipping containers of this type to the port of origin.</span></span> |

## <a name="set-up-shipping-containers"></a><span data-ttu-id="301f2-123">Konfigurowanie kontenerów przewozowych</span><span class="sxs-lookup"><span data-stu-id="301f2-123">Set up shipping containers</span></span>

<span data-ttu-id="301f2-124">Rekordów kontenerów wysyłkowych można używać do identyfikowania każdego kontenera podczas podróży.</span><span class="sxs-lookup"><span data-stu-id="301f2-124">You use shipping container records to identify each container that you use during voyages.</span></span> <span data-ttu-id="301f2-125">Tworząc podróż, możesz wybrać dla niej określony kontener z listy wszystkich zapisów kontenerów wysyłkowych, które zdefiniowałeś w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="301f2-125">When you create a voyage, you can select a specific container for it in the list of all the shipping container records that you've defined here.</span></span> <span data-ttu-id="301f2-126">Ta funkcja jest szczególnie przydatna, jeśli firma posiada własne kontenery wysyłkowe.</span><span class="sxs-lookup"><span data-stu-id="301f2-126">This feature is especially useful if your company owns its own shipping containers.</span></span>

<span data-ttu-id="301f2-127">Nie trzeba wprowadzać numerów kontenerów wysyłkowych dla kontenerów wysyłkowych, które będą używane tylko jeden raz.</span><span class="sxs-lookup"><span data-stu-id="301f2-127">You don't have to enter shipping container numbers for shipping containers that will be used only one time.</span></span> <span data-ttu-id="301f2-128">Zamiast tego można dodać numer kontenera wysyłkowego podczas tworzenia podróży.</span><span class="sxs-lookup"><span data-stu-id="301f2-128">Instead, you can add the shipping container number when you create a voyage.</span></span>

<span data-ttu-id="301f2-129">Rekordy kontenerów wysyłkowych są używane tylko w rekordzie Koszt z wyładunkiem.</span><span class="sxs-lookup"><span data-stu-id="301f2-129">Shipping container records are used only in Landed cost.</span></span> <span data-ttu-id="301f2-130">Nie są one dostępne w standardowym module **Zarządzania transportem** (TMS).</span><span class="sxs-lookup"><span data-stu-id="301f2-130">They aren't available in the standard **Transportation management** module (TMS).</span></span>

<span data-ttu-id="301f2-131">Aby pracować z kontenerami wysyłkowymi, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Kontenery wysyłkowe**.</span><span class="sxs-lookup"><span data-stu-id="301f2-131">To work with shipping containers, go to **Landed cost \> Containers setup \> Shipping containers**.</span></span> <span data-ttu-id="301f2-132">Możesz tam przeglądać, dodawać i usuwać zapisy swoich kontenerów transportowych.</span><span class="sxs-lookup"><span data-stu-id="301f2-132">There, you can view, add, and remove records your shipping containers.</span></span> <span data-ttu-id="301f2-133">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="301f2-133">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="301f2-134">Pole</span><span class="sxs-lookup"><span data-stu-id="301f2-134">Field</span></span> | <span data-ttu-id="301f2-135">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-135">Description</span></span> |
|---|---|
| <span data-ttu-id="301f2-136">Kontener wysyłkowy</span><span class="sxs-lookup"><span data-stu-id="301f2-136">Shipping container</span></span> | <span data-ttu-id="301f2-137">Wprowadź unikalną nazwę/numer identyfikacyjny kontenera.</span><span class="sxs-lookup"><span data-stu-id="301f2-137">Enter a unique identification name/number for the shipping container.</span></span> |
| <span data-ttu-id="301f2-138">Typ kontenera wysyłkowego</span><span class="sxs-lookup"><span data-stu-id="301f2-138">Shipping container type</span></span> | <span data-ttu-id="301f2-139">Wybierz typ kontenera wysyłkowego.</span><span class="sxs-lookup"><span data-stu-id="301f2-139">Select the type of shipping container.</span></span> <span data-ttu-id="301f2-140">Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie typów kontenerów wysyłkowych](#shipping-container-types) we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="301f2-140">For more information, see the [Set up shipping container types](#shipping-container-types) section earlier in this topic.</span></span> |

> [!NOTE]
> - <span data-ttu-id="301f2-141">Konfiguracja kontenera wysyłkowego jest opcjonalna.</span><span class="sxs-lookup"><span data-stu-id="301f2-141">The shipping container setup is optional.</span></span> <span data-ttu-id="301f2-142">Zwykle będziesz go używać tylko wtedy, gdy Twoja firma posiada własne kontenery transportowe lub często ponownie wykorzystuje te same kontenery transportowe.</span><span class="sxs-lookup"><span data-stu-id="301f2-142">Typically, you will use it only if your company owns its own shipping containers or often reuses the same shipping containers.</span></span>
> - <span data-ttu-id="301f2-143">Nie obliczono cyfr kontrolnych dla numerów kontenerów wysyłkowych.</span><span class="sxs-lookup"><span data-stu-id="301f2-143">No check digits are calculated for shipping container numbers.</span></span>

## <a name="set-up-unit-types"></a><a name="unit-types"></a><span data-ttu-id="301f2-144">Skonfiguruj typy jednostek</span><span class="sxs-lookup"><span data-stu-id="301f2-144">Set up unit types</span></span>

<span data-ttu-id="301f2-145">Typy jednostek określają dodatkowe grupy i metody identyfikacji kontenerów transportowych.</span><span class="sxs-lookup"><span data-stu-id="301f2-145">Unit types establish additional groupings and identification methods for shipping containers.</span></span> <span data-ttu-id="301f2-146">Typ jednostki jest zwykle używany do identyfikacji rodzaju kontenera, w którym pakowane są towary, takiego jak palety lub beczki.</span><span class="sxs-lookup"><span data-stu-id="301f2-146">The unit type is typically used to identify the type of container that goods are packaged in, such as pallets or drums.</span></span> <span data-ttu-id="301f2-147">Typ jednostki można wybrać podczas konfigurowanie kontenera na stronie **Wszystkie kontenery wysyłkowe**.</span><span class="sxs-lookup"><span data-stu-id="301f2-147">You can select a unit type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="301f2-148">Typy jednostek są używane tylko w kosztach z wyładunkiem.</span><span class="sxs-lookup"><span data-stu-id="301f2-148">Unit types are used only in Landed cost.</span></span> <span data-ttu-id="301f2-149">Nie są dostępne w TMS.</span><span class="sxs-lookup"><span data-stu-id="301f2-149">They aren't available in TMS.</span></span>

<span data-ttu-id="301f2-150">Aby pracować z typami jednostek, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Typy jednostek**.</span><span class="sxs-lookup"><span data-stu-id="301f2-150">To work with unit types, go to **Landed cost \> Containers setup \> Unit types**.</span></span> <span data-ttu-id="301f2-151">Można tam wyświetlać, dodawać i usuwać rekordy typów jednostek.</span><span class="sxs-lookup"><span data-stu-id="301f2-151">There, you can view, add, and remove records for your unit types.</span></span> <span data-ttu-id="301f2-152">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="301f2-152">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="301f2-153">Pole</span><span class="sxs-lookup"><span data-stu-id="301f2-153">Field</span></span> | <span data-ttu-id="301f2-154">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-154">Description</span></span> |
|---|---|
| <span data-ttu-id="301f2-155">Typ jednostki</span><span class="sxs-lookup"><span data-stu-id="301f2-155">Unit type</span></span> | <span data-ttu-id="301f2-156">Wprowadź unikalną nazwę/numer identyfikacyjny typu jednostek.</span><span class="sxs-lookup"><span data-stu-id="301f2-156">Enter a unique identification name/number for the unit type.</span></span> |
| <span data-ttu-id="301f2-157">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-157">Description</span></span> | <span data-ttu-id="301f2-158">Umożliwia wprowadzenie opisu typu jednostki.</span><span class="sxs-lookup"><span data-stu-id="301f2-158">Enter a description of the unit type.</span></span> |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a><span data-ttu-id="301f2-159">Skonfiguruj typy chłodnictwa</span><span class="sxs-lookup"><span data-stu-id="301f2-159">Set up refrigeration types</span></span>

<span data-ttu-id="301f2-160">Typy chłodzenia określają dodatkowe grupy i metody identyfikacji kontenerów wysyłkowych (zwykle kontenerów chłodniczych).</span><span class="sxs-lookup"><span data-stu-id="301f2-160">Refrigeration types establish additional groupings and identification methods for shipping containers (usually refrigerated containers).</span></span> <span data-ttu-id="301f2-161">Typ chłodzenia można wybrać podczas konfigurowanie kontenera na stronie **Wszystkie kontenery wysyłkowe**.</span><span class="sxs-lookup"><span data-stu-id="301f2-161">You can select a refrigeration type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="301f2-162">Aby pracować z typami chłodzenia, przejdź do **Koszt z wyładunkiem \> Konfiguracja kontenera \> Typy chłodzenia**.</span><span class="sxs-lookup"><span data-stu-id="301f2-162">To work with refrigeration types, go to **Landed cost \> Containers setup \> Refrigeration types**.</span></span> <span data-ttu-id="301f2-163">Można tam wyświetlać, dodawać i usuwać rekordy typów chłodzenia.</span><span class="sxs-lookup"><span data-stu-id="301f2-163">There, you can view, add, and remove records for your refrigeration types.</span></span> <span data-ttu-id="301f2-164">W poniższej tabeli przedstawiono pola dostępne w nagłówku dla każdego zapisu.</span><span class="sxs-lookup"><span data-stu-id="301f2-164">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="301f2-165">Pole</span><span class="sxs-lookup"><span data-stu-id="301f2-165">Field</span></span> | <span data-ttu-id="301f2-166">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-166">Description</span></span> |
|---|---|
| <span data-ttu-id="301f2-167">Typ systemu chłodzenia</span><span class="sxs-lookup"><span data-stu-id="301f2-167">Refrigeration type</span></span> | <span data-ttu-id="301f2-168">Wprowadź unikalną nazwę/numer identyfikacyjny typu chłodzenia.</span><span class="sxs-lookup"><span data-stu-id="301f2-168">Enter a unique identification name/number for the refrigeration type.</span></span> |
| <span data-ttu-id="301f2-169">opis</span><span class="sxs-lookup"><span data-stu-id="301f2-169">Description</span></span> | <span data-ttu-id="301f2-170">Wprowadź opis typu chłodzenia.</span><span class="sxs-lookup"><span data-stu-id="301f2-170">Enter a description of the refrigeration type.</span></span> |
