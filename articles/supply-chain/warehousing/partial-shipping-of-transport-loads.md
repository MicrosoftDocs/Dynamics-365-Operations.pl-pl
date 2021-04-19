---
title: Częściowa dostawa ładunku w transporcie
description: W tym temacie wyjaśniono, jak można częściowo wysłać ładunek i odłożyć planowania pojemności dla ładunku.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 179a784f1f02ed0840ba5219c350e274272b59eb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818951"
---
# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="e81a1-103">Częściowa dostawa ładunku w transporcie</span><span class="sxs-lookup"><span data-stu-id="e81a1-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e81a1-104">Konfigurując częściową wysyłkę ładunków, można obsługiwać ładunki, gdy pojemność daje się określić dopiero po dodaniu wszystkich wierszy sprzedaży do ładunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="e81a1-105">Następnie, gdy jest znana dokładna liczba palet, można sfinalizować proces.</span><span class="sxs-lookup"><span data-stu-id="e81a1-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="e81a1-106">Dzięki temu nie trzeba decydować, które palety zostaną przypisane do którego transportu, aż do chwili, gdy transport zostanie fizycznie załadowany z przygotowanych zapasów.</span><span class="sxs-lookup"><span data-stu-id="e81a1-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="e81a1-107">Ta funkcja oferuje alternatywę wobec egzekwowania bardziej sztywnej struktury, gdzie trzeba określić, które palety zostaną przypisane do którego transportu, zanim będzie można utworzyć pracę pobrania lub załadunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="e81a1-108">Zamiast tego użytkownicy mogą skonfigurować poszczególne ładunki na potrzeby potwierdzenia dostawy częściowej.</span><span class="sxs-lookup"><span data-stu-id="e81a1-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="e81a1-109">Wtedy mogą nastąpić procesy umieszczenia tych ładunków w środku transportu ładunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="e81a1-110">Dzięki temu dział planowania transportu może planować ładunki bez konieczności brania pod uwagę pojemności poszczególnych transportów.</span><span class="sxs-lookup"><span data-stu-id="e81a1-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="e81a1-111">W momencie załadunku pracownicy mogą zdefiniować nowy środek transportu ładunku, do którego można załadować paletę.</span><span class="sxs-lookup"><span data-stu-id="e81a1-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="e81a1-112">Alternatywnie mogą wskazać istniejący środek transportu ładunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="e81a1-113">Te dane można rejestrować za pomocą urządzenia przenośnego.</span><span class="sxs-lookup"><span data-stu-id="e81a1-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="e81a1-114">W efekcie kilku pracowników magazynu może ładować zapasy z tych samych lub różnych ładunków na tę samą ciężarówkę.</span><span class="sxs-lookup"><span data-stu-id="e81a1-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="e81a1-115">Następnie ładunki można w pełni lub częściowo wysłać.</span><span class="sxs-lookup"><span data-stu-id="e81a1-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="e81a1-116">Aby załadować zapasy z ładunku do konkretnego środka transportu ładunku i częściowo wysłać, należy wygenerować pracę, używając klasy załadunku w szablonie pracy.</span><span class="sxs-lookup"><span data-stu-id="e81a1-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="e81a1-117">Zwykła praca pobrania o typie **Pobranie** nie może służyć do ładowania do środka transportu ładunku, takiego jak ciężarówka.</span><span class="sxs-lookup"><span data-stu-id="e81a1-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="e81a1-118">Konfigurowanie środków transportu ładunku dla wysyłki częściowej</span><span class="sxs-lookup"><span data-stu-id="e81a1-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="e81a1-119">Konfiguracja częściowej wysyłki ładunki składa się z dwóch poniższych procedur.</span><span class="sxs-lookup"><span data-stu-id="e81a1-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="e81a1-120">Konfigurowanie strategii załadunku</span><span class="sxs-lookup"><span data-stu-id="e81a1-120">Set the loading strategy</span></span>

<span data-ttu-id="e81a1-121">Należy włączyć załadunek częściowy poprzez ustawienie strategii załadunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="e81a1-122">Strategię załadunku można ustawić po utworzeniu ładunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="e81a1-123">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ładunki** \> **Wszystkie ładunki**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="e81a1-124">Wybierz ładunek i kliknij opcję **Nagłówek**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="e81a1-125">W polu **Strategia ładowania** zaznacz opcję **Dozwolona częściowa wysyłka ładunku**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="e81a1-126">Tworzenie elementu menu dla załadunku na środki transportu ładunku</span><span class="sxs-lookup"><span data-stu-id="e81a1-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="e81a1-127">Należy utworzyć nowy element menu, który umożliwi załadunek na środki transportu ładunku.</span><span class="sxs-lookup"><span data-stu-id="e81a1-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="e81a1-128">Środek transportu ładunku pozwala grupować wiersze pracy z jednego ładunku lub wielu ładunków.</span><span class="sxs-lookup"><span data-stu-id="e81a1-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="e81a1-129">Wszystko, co zostanie dodane do środka transportu ładunku, można następnie wysłać przy użyciu skanera przenośnego.</span><span class="sxs-lookup"><span data-stu-id="e81a1-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="e81a1-130">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="e81a1-131">Wybierz opcję **Nowy**, a następnie w polu **Tryb** wybierz opcję **Praca**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="e81a1-132">W opcji **Użyj istniejącej pracy** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="e81a1-133">Na karcie **Ogólne** w polu **Sterowane przez** wybierz opcję **Ładowanie transportu**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="e81a1-134">Aby włączyć potwierdzania wysyłki na przenośnym skanerze, w polu **Dozwolony typ potwierdzenia wysyłki** wybierz opcję **Ładunek w transporcie**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="e81a1-135">Potwierdzanie wysyłki środka transportu ładunku z klienta</span><span class="sxs-lookup"><span data-stu-id="e81a1-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="e81a1-136">Ta konfiguracja umożliwia potwierdzenie środka transportu ładunku, który zawiera ładunek pełny lub częściowy przeznaczony do wysłania.</span><span class="sxs-lookup"><span data-stu-id="e81a1-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="e81a1-137">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ładunki** \> **Ładunki w transporcie**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="e81a1-138">W okienku akcji na karcie **Wyślij i odbierz** w grupie **Potwierdź** kliknij opcję **Transport**.</span><span class="sxs-lookup"><span data-stu-id="e81a1-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]