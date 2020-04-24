---
title: Konfiguruj pobieranie dla grupy
description: W tym temacie opisano sposób konfigurowania funkcji pobierania dla grupy oraz stosowania potwierdzania towaru z pobieraniem dla grupy.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: daf8bc65dc937962e2e08b6f25805ddd3b8ee3c5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204293"
---
[!include[banner](../includes/banner.md)]

# <a name="set-up-cluster-picking"></a><span data-ttu-id="642ab-103">Konfiguruj pobieranie dla grupy</span><span class="sxs-lookup"><span data-stu-id="642ab-103">Set up cluster picking</span></span>

<span data-ttu-id="642ab-104">W tym temacie opisano sposób umożliwienia pracownikom korzystania z urządzeń przenośnych do pobierania grupowania pracy pobrania, w celu umożliwienia pobrania towarów z jednej lokalizacji dla wielu zleceń pracy w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="642ab-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="642ab-105">Nazywa się to *pobieraniem dla grup*.</span><span class="sxs-lookup"><span data-stu-id="642ab-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="642ab-106">Pobieranie dla grupy — informacje</span><span class="sxs-lookup"><span data-stu-id="642ab-106">About cluster picking</span></span>

<span data-ttu-id="642ab-107">Po zwolnieniu zleceń pracy do magazynu, pracownik może użyć urządzenia przenośnego do przypisywania zamówień do grupy.</span><span class="sxs-lookup"><span data-stu-id="642ab-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="642ab-108">Grupa organizuje pracę pobrania dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="642ab-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="642ab-109">Po przypisaniu zlecenia pracy do grupy, pracownik należy użyć pobierania dla grupy do wykonania pracy pobrania dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="642ab-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="642ab-110">Pracownik nie może stosować innych metod pobierania.</span><span class="sxs-lookup"><span data-stu-id="642ab-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="642ab-111">Jeśli zlecenie pracy jest przypisane do grupy przez pomyłkę, pracownik musi podzielić grupę i następnie utworzyć ją ponownie.</span><span class="sxs-lookup"><span data-stu-id="642ab-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="642ab-112">W razie potrzeby, pracownik może przekazać grupę innemu pracownikowi.</span><span class="sxs-lookup"><span data-stu-id="642ab-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="642ab-113">Powoduje to zmianę stanu grupy na Zdany.</span><span class="sxs-lookup"><span data-stu-id="642ab-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="642ab-114">Jeżeli pracownik używa urządzenia przenośnego do wskazania, że praca pobierania i odkładania została zakończona, wysyłka lub załadunek muszą zostać potwierdzone na kliencie.</span><span class="sxs-lookup"><span data-stu-id="642ab-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the client.</span></span>

## <a name="set-up-cluster-picking"></a><span data-ttu-id="642ab-115">Konfigurowanie pobierania dla grupy</span><span class="sxs-lookup"><span data-stu-id="642ab-115">Set up cluster picking</span></span>

<span data-ttu-id="642ab-116">Aby włączyć pobieranie dla grupy, należy skonfigurować następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="642ab-116">To enable cluster picking, you must set up the following:</span></span>

-   <span data-ttu-id="642ab-117">**Profile grup** — Umożliwia określenie, czy automatycznie generować identyfikatory grupy, liczbę pozycji do użycia, kiedy likwidować grupy i jak ustawiać sekwencje i przeprowadzać sprawdzanie dla pracy pobierania.</span><span class="sxs-lookup"><span data-stu-id="642ab-117">**Cluster profiles** – Specify whether to automatically generate cluster IDs, the number of positions to use, when to break clusters, and how to sequence and verify the picking work.</span></span>

-   <span data-ttu-id="642ab-118">**Szablony pracy** — Umożliwia definiowanie sposobu tworzenia pracy pobierania dla pobierania dla grup.</span><span class="sxs-lookup"><span data-stu-id="642ab-118">**Work templates** – Define how to create the picking work for cluster picking.</span></span>

-   <span data-ttu-id="642ab-119">**Dyrektywy lokalizacji** — Umożliwia określenie miejsca pobierania towarów i miejsca ich odkładania.</span><span class="sxs-lookup"><span data-stu-id="642ab-119">**Location directives** – Specify where to pick items from, and where to put them.</span></span>

-   <span data-ttu-id="642ab-120">**Elementy menu urządzenia przenośnego** — Umożliwia skonfigurowanie menu urządzenia przenośnego do wykorzystania istniejącej pracy, która jest sterowana przez pobieranie dla grup.</span><span class="sxs-lookup"><span data-stu-id="642ab-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="642ab-121">Następnie należy dodać element menu do menu urządzenia przenośnego, tak aby był wyświetlany na urządzeniach przenośnych.</span><span class="sxs-lookup"><span data-stu-id="642ab-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

-   <span data-ttu-id="642ab-122">**Parametry zarządzania magazynem** — Służy do określenia numeracji, która ma być używana, jeśli chcesz wygenerować identyfikatory grup.</span><span class="sxs-lookup"><span data-stu-id="642ab-122">**Warehouse management parameters** – Specify the number sequence to use if you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="642ab-123">Konfigurowanie profilu grupy</span><span class="sxs-lookup"><span data-stu-id="642ab-123">Set up a cluster profile</span></span>

<span data-ttu-id="642ab-124">Aby skonfigurować profil grupy, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="642ab-124">To set up a cluster profile, follow these steps:</span></span>

1.  <span data-ttu-id="642ab-125">Kliknij kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Profile grup**.</span><span class="sxs-lookup"><span data-stu-id="642ab-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \> **Cluster profiles**.</span></span>

2.  <span data-ttu-id="642ab-126">Kliknij przycisk **Nowy**, aby utworzyć nowy profil.</span><span class="sxs-lookup"><span data-stu-id="642ab-126">Click **New** to create a new profile.</span></span>

3.  <span data-ttu-id="642ab-127">Kliknij przycisk **Tworzenie grupy**, a następnie w obszarze **Sortowanie grup** kliknij przycisk **Nowy**, aby skonfigurować kryteria sortowania grupy.</span><span class="sxs-lookup"><span data-stu-id="642ab-127">Click **Create cluster** and, under **Cluster sorting**, click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="642ab-128">Kryteria sortowania kontrolują kolejność, w której pracownik będzie wykonywał pracę pobierania.</span><span class="sxs-lookup"><span data-stu-id="642ab-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="642ab-129">Można dodać dowolną liczbę kryteriów.</span><span class="sxs-lookup"><span data-stu-id="642ab-129">You can add as many criteria as needed.</span></span>

4.  <span data-ttu-id="642ab-130">W polu **Numer sekwencyjny** wprowadź liczbę określającą kolejność, w jakiej mają być przetwarzane kryteria sortowania.</span><span class="sxs-lookup"><span data-stu-id="642ab-130">In the **Sequence number** field, enter a number to define the order in which the sorting criteria are processed.</span></span>

5.  <span data-ttu-id="642ab-131">W polu **Nazwa pola**, wybierz pole, które będzie określać sortowanie.</span><span class="sxs-lookup"><span data-stu-id="642ab-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="642ab-132">Na przykład, jeśli wybierzesz pole **WMSLocationId**, praca zostanie posortowana według lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="642ab-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

6.  <span data-ttu-id="642ab-133">W polu **Sortowanie** wybierz jedną z poniższych opcji.</span><span class="sxs-lookup"><span data-stu-id="642ab-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="642ab-134">**Opcja**</span><span class="sxs-lookup"><span data-stu-id="642ab-134">**Option**</span></span>     | <span data-ttu-id="642ab-135">**Opis**</span><span class="sxs-lookup"><span data-stu-id="642ab-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="642ab-136">**Rosnąco**</span><span class="sxs-lookup"><span data-stu-id="642ab-136">**Ascending**</span></span>  | <span data-ttu-id="642ab-137">Praca pobierania jest uporządkowana w kolejności rosnącej, na podstawie kryteriów sortowania.</span><span class="sxs-lookup"><span data-stu-id="642ab-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="642ab-138">Na przykład, jeśli używasz pola **WMSLocationId** jako kryterium sortowania, a dana nazwa lokalizacji to 1, 2, 3 i 4, najpierw wybrana zostanie lokalizacja 4.</span><span class="sxs-lookup"><span data-stu-id="642ab-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="642ab-139">**Malejąco**</span><span class="sxs-lookup"><span data-stu-id="642ab-139">**Descending**</span></span> | <span data-ttu-id="642ab-140">Praca pobierania jest uporządkowana w kolejności malejącej, na podstawie kryteriów sortowania.</span><span class="sxs-lookup"><span data-stu-id="642ab-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="642ab-141">Na przykład, jeśli używasz pola **WMSLocationId** jako kryterium sortowania, a dana nazwa lokalizacji to 1, 2, 3 i 4, najpierw wybrana zostanie lokalizacja 1.</span><span class="sxs-lookup"><span data-stu-id="642ab-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="642ab-142">Potwierdzanie towarów</span><span class="sxs-lookup"><span data-stu-id="642ab-142">Item confirmation</span></span>

<span data-ttu-id="642ab-143">W przypadku stosowania pobierania dla grupy bardzo ważne jest potwierdzanie towarów dodawanych do grup.</span><span class="sxs-lookup"><span data-stu-id="642ab-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="642ab-144">Weryfikowanie może się odbywać w trakcie procesu pobierania dla grup.</span><span class="sxs-lookup"><span data-stu-id="642ab-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="642ab-145">Konfiguracja zależy od ustawień kodów kreskowych produktów.</span><span class="sxs-lookup"><span data-stu-id="642ab-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="642ab-146">Konfigurowanie weryfikowania towarów w trakcie pobierania dla grupy</span><span class="sxs-lookup"><span data-stu-id="642ab-146">Set up item verification with cluster picking</span></span>

1.  <span data-ttu-id="642ab-147">Na urządzeniu przenośnym w menu otwórz formularz ustawień potwierdzenia pracy: **Zarządzanie magazynem** \> **Zarządzanie magazynem** \> **Ustawienia** \> **Urządzenie przenośne** \> **Elementy menu urządzenia przenośnego**.</span><span class="sxs-lookup"><span data-stu-id="642ab-147">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** \> **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>

2.  <span data-ttu-id="642ab-148">Na urządzeniu przenośnym w menu otwórz pozycję **Konfiguracja potwierdzenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="642ab-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="642ab-149">Opcja **Potwierdzenie produktu** umożliwia weryfikowanie każdego artykułu w zapasach z urządzenia przenośnego podczas skanowania.</span><span class="sxs-lookup"><span data-stu-id="642ab-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>
