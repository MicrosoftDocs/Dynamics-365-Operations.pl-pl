---
title: Dodatkowe strefy lokalizacji
description: Ten temat zawiera przegląd nowych stref lokalizacji, które zostały dodane do rozwiązania Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 6cf81939989b8faffcda51bbbd5bc6b27aec7eea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435589"
---
# <a name="additional-location-zones"></a><span data-ttu-id="291e3-103">Dodatkowe strefy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="291e3-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="291e3-104">W rozwiązaniu Microsoft Dynamics 365 Supply Chain Management są dostępne trzy nowe pola strefy.</span><span class="sxs-lookup"><span data-stu-id="291e3-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="291e3-105">Kierownicy magazynów mogą używać ich do stworzenia dodatkowych organizacji lub układów magazynu.</span><span class="sxs-lookup"><span data-stu-id="291e3-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="291e3-106">Nowe pola stref można ustawiać ręcznie lub przy użyciu kreatora **konfiguracji lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="291e3-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="291e3-107">Można ich używać w dowolnej kwerendzie lub filtrowaniu, w której jest używana tabela lokalizacje.</span><span class="sxs-lookup"><span data-stu-id="291e3-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="291e3-108">Do użycia pól strefy nie są wymagane żadne dodatkowe ustawienia.</span><span class="sxs-lookup"><span data-stu-id="291e3-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="291e3-109">Włącz funkcję dodatkowej strefy lokalizacji</span><span class="sxs-lookup"><span data-stu-id="291e3-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="291e3-110">Aby móc używać funkcji *Dodatkowa strefa lokalizacji*, należy ją włączyć w systemie.</span><span class="sxs-lookup"><span data-stu-id="291e3-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="291e3-111">Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba.</span><span class="sxs-lookup"><span data-stu-id="291e3-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="291e3-112">W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:</span><span class="sxs-lookup"><span data-stu-id="291e3-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="291e3-113">**Moduł:** *Zarządzanie magazynem*</span><span class="sxs-lookup"><span data-stu-id="291e3-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="291e3-114">**Nazwa funkcji:** *Dodatkowa strefa lokalizacji*</span><span class="sxs-lookup"><span data-stu-id="291e3-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="291e3-115">Używanie stref lokalizacji</span><span class="sxs-lookup"><span data-stu-id="291e3-115">Use location zones</span></span>

1. <span data-ttu-id="291e3-116">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Profile lokalizacji**.</span><span class="sxs-lookup"><span data-stu-id="291e3-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="291e3-117">Ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="291e3-117">Set the following values:</span></span>

    - <span data-ttu-id="291e3-118">W polu **Magazyn** wybierz wartość _62_.</span><span class="sxs-lookup"><span data-stu-id="291e3-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="291e3-119">W polu **Identyfikator strefy** wpisz wartość _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="291e3-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="291e3-120">W polu **Dodatkowa strefa 1** wybierz wartość _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="291e3-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="291e3-121">W polu **Dodatkowa strefa 2** wybierz wartość _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="291e3-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="291e3-122">W polu **Identyfikator profilu lokalizacji** wybierz _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="291e3-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="291e3-123">Wybierz wiersz **Piętro**.</span><span class="sxs-lookup"><span data-stu-id="291e3-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="291e3-124">W polu **Od numeru** wprowadź wartość _1_.</span><span class="sxs-lookup"><span data-stu-id="291e3-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="291e3-125">W polu **Do numeru** wprowadź wartość _3_.</span><span class="sxs-lookup"><span data-stu-id="291e3-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="291e3-126">Wybierz wiersz **Korytarz**.</span><span class="sxs-lookup"><span data-stu-id="291e3-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="291e3-127">W polu **Od numeru** wprowadź wartość _1_.</span><span class="sxs-lookup"><span data-stu-id="291e3-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="291e3-128">W polu **Do numeru** wprowadź wartość _5_.</span><span class="sxs-lookup"><span data-stu-id="291e3-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="291e3-129">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="291e3-129">Select **Create**.</span></span>
8. <span data-ttu-id="291e3-130">Otrzymujesz komunikaty informujące o dodaniu nowych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="291e3-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="291e3-131">Wybierz przycisk **Pokaż komunikaty**, aby wyświetlić komunikaty.</span><span class="sxs-lookup"><span data-stu-id="291e3-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="291e3-132">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Magazyn \> Lokalizacje**.</span><span class="sxs-lookup"><span data-stu-id="291e3-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="291e3-133">Nowe lokalizacje są wyświetlane na liście – dostępne są wszystkie pola strefy (to znaczy, istniejące pole strefy i nowe dodatkowe pola).</span><span class="sxs-lookup"><span data-stu-id="291e3-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
