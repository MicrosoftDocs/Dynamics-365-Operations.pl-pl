---
title: Przenoszenie zapasów za pomocą skojarzonej pracy w module Zarządzanie magazynem
description: W tym temacie opisano sposób konfigurowania i stosowania potwierdzenia pobrania sztuk z urządzenia przenośnego.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aee3af8da6610c16fc2d98091bfa3f01f1bd0f5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215730"
---
# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="eea5d-103">Przenoszenie zapasów za pomocą skojarzonej pracy w module Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="eea5d-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eea5d-104">Za pomocą przesunięcia zapasów użytkownik może zdecydować, którzy pracownicy magazynu będą mogli przenosić zarezerwowane zapasy.</span><span class="sxs-lookup"><span data-stu-id="eea5d-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="eea5d-105">Zapewnia to elastyczność w magazynach regulowanych, gdzie można zdecydować, aby nie zezwolić pracownikowi na wybieranie nowej lokalizacji pobrania dla już utworzonej pracy pobrania.</span><span class="sxs-lookup"><span data-stu-id="eea5d-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="eea5d-106">Umożliwia to również kierownikowi magazynu kontrolowanie, jakie możliwości powinni mieć niektórzy mniej doświadczeni pracownicy.</span><span class="sxs-lookup"><span data-stu-id="eea5d-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="eea5d-107">Elastyczność zarządzania codziennymi operacjami pracowników magazynu może być przydatne w scenariuszach takich jak te:</span><span class="sxs-lookup"><span data-stu-id="eea5d-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="eea5d-108">Scenariusz 1</span><span class="sxs-lookup"><span data-stu-id="eea5d-108">Scenario 1</span></span>
<span data-ttu-id="eea5d-109">Firma ma stosunkowo mały obszar przyjęcia i jest on zatłoczony paletami i pudełkami oczekującymi na odłożenie.</span><span class="sxs-lookup"><span data-stu-id="eea5d-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="eea5d-110">Danego dnia jest oczekiwana duża przesyłka, więc pracownik przyjmujący decyduje się na wyczyszczenie obszaru przyjęcia poprzez przeniesienie niektórych palet do pomocniczego obszaru pośredniego rozładunku.</span><span class="sxs-lookup"><span data-stu-id="eea5d-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="eea5d-111">Scenariusz 2</span><span class="sxs-lookup"><span data-stu-id="eea5d-111">Scenario 2</span></span>
<span data-ttu-id="eea5d-112">Doświadczony pracownik magazynu zauważył w magazynie możliwość skonsolidowania towarów w jednym miejscu zamiast je dzielić między 3 znajdujące się blisko siebie lokalizacje z małą ilością w każdej z nich.</span><span class="sxs-lookup"><span data-stu-id="eea5d-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="eea5d-113">Pracownik chce skonsolidować ilości, przenosząc towary z każdej lokalizacji do tej samej lokalizacji i na ten sam numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="eea5d-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="eea5d-114">Scenariusz 3</span><span class="sxs-lookup"><span data-stu-id="eea5d-114">Scenario 3</span></span>
<span data-ttu-id="eea5d-115">Paleta oczekuje na wysyłkę w lokalizacji pośredniej, takiej jak STAGE01, która znajduje się w pobliżu bramy dokowej BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="eea5d-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="eea5d-116">Jednak z powodu zmiany planów ciężarówka ma podjechać do bramy dokowej BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="eea5d-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="eea5d-117">Pracownik ds. spedycji wie o tym i musi się upewnić, że ciężarówka nie będzie musiała czekać na załadunek z lokalizacji STAGE01.</span><span class="sxs-lookup"><span data-stu-id="eea5d-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="eea5d-118">Dlatego pracownik decyduje się przenieść towary tej wysyłki z lokalizacji STAGE01 do lokalizacji STAGE04, która znajduje się bliżej nowego miejsca docelowego.</span><span class="sxs-lookup"><span data-stu-id="eea5d-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="eea5d-119">Bieżące ograniczenia</span><span class="sxs-lookup"><span data-stu-id="eea5d-119">Current limitations</span></span>

<span data-ttu-id="eea5d-120">Rezerwacje pracy, które można przenosić, są ograniczone do zamówienia sprzedaży, wydania zamówienia przeniesienia, przyjęcia zamówienia przeniesienia, zamówienia zakupu i pracy uzupełniania zapasów.</span><span class="sxs-lookup"><span data-stu-id="eea5d-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="eea5d-121">Przenoszenie towarów jest ograniczone w celu zapobieżenia dzieleniu wierszy pracy.</span><span class="sxs-lookup"><span data-stu-id="eea5d-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="eea5d-122">Oznacza to, że jeśli masz wiersz pracy na 100 sztuk towaru A z lokalizacji Loc1, nie będzie można przenieść tylko 30 sztuk towaru A z tej lokalizacji do innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="eea5d-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="eea5d-123">To doprowadziłoby do podziału istniejącego wiersza pracy na 30 i 70 sztuk, ponieważ lokalizacje teraz są różne.</span><span class="sxs-lookup"><span data-stu-id="eea5d-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="eea5d-124">W scenariuszach z lokalizacjami pośrednimi, gdzie numer identyfikacyjny, z którego lub pod który są przesuwane towary, są ustawione jako docelowy numer identyfikacyjny dla zlecenia produkcyjnego, można przesuwać tylko całą zawartość numeru identyfikacyjnego, tak aby nie podzielić zawartości docelowego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="eea5d-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="eea5d-125">Obecnie są obsługiwane tylko przesunięcia ad hoc.</span><span class="sxs-lookup"><span data-stu-id="eea5d-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="eea5d-126">Oznacza to, że nie będzie można przesuwać zarezerwowanych zapasów za pomocą przesunięć przy użyciu elementów menu szablonu na urządzeniu przenośnym.</span><span class="sxs-lookup"><span data-stu-id="eea5d-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="eea5d-127">Ustawianie uprawnień do przesuwania zarezerwowanych zapasów dla poszczególnych pracowników</span><span class="sxs-lookup"><span data-stu-id="eea5d-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="eea5d-128">Dla pracownika, który powinien mieć możliwość przesuwania zarezerwowanych zapasów, należy zaznaczyć pole wyboru **Zezwalaj na przesuwanie zapasów za pomocą skojarzonej pracy** w obszarze **Zarządzanie magazynem** > **ustawienia** > **Pracownik**.</span><span class="sxs-lookup"><span data-stu-id="eea5d-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="eea5d-129">Dodanie w starszych wersjach</span><span class="sxs-lookup"><span data-stu-id="eea5d-129">Backported</span></span>

<span data-ttu-id="eea5d-130">Ta funkcja została także dodana wstecznie do systemu Microsoft Dynamics AX 2012 R3 i będzie dostępna w ramach zbiorczej aktualizacji CU12.</span><span class="sxs-lookup"><span data-stu-id="eea5d-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="eea5d-131">Ponadto można ją pobrać oddzielnie jako pakiet KB 3192548.</span><span class="sxs-lookup"><span data-stu-id="eea5d-131">It can also be downloaded individually through KB number 3192548.</span></span> 

