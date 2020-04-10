---
title: Zmiana własności zapasów konsygnacyjnych w oparciu o zapotrzebowanie produkcyjne
description: Ta procedura pokazuje, jak zmienić właściciela zapasów konsygnacyjnych z dostawcy na firmę, gdy istnieje zapotrzebowanie na zapasy w produkcji.
author: perlynne
manager: AnnBe
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8200e0235fa78cbef4fdadd1d1c124446b89e72a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145892"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="d4df4-103">Zmiana własności zapasów konsygnacyjnych w oparciu o zapotrzebowanie produkcyjne</span><span class="sxs-lookup"><span data-stu-id="d4df4-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4df4-104">Ta procedura pokazuje, jak zmienić właściciela zapasów konsygnacyjnych z dostawcy na firmę, gdy istnieje zapotrzebowanie na zapasy w produkcji.</span><span class="sxs-lookup"><span data-stu-id="d4df4-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="d4df4-105">Ta zmiana własności odbywa się poprzez utworzenie i zaksięgowanie arkusza zmiany własności zapasów.</span><span class="sxs-lookup"><span data-stu-id="d4df4-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="d4df4-106">Wiersze arkusza zmiany własności można tworzyć ręcznie lub, jak pokazano w tym nagraniu, na podstawie istniejącego zapotrzebowania produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d4df4-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="d4df4-107">Zazwyczaj to zadanie wykonuje kierownik zakładu produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="d4df4-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="d4df4-108">Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.</span><span class="sxs-lookup"><span data-stu-id="d4df4-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="d4df4-109">Jeśli korzystasz z własnych danych, upewnij się, że istnieją następujące warunki wstępne: nazwa arkusza magazynowego skonfigurowana dla zmiany własności zapasów, fizycznie zarejestrowane dostępne towary będące własnością dostawcy oraz jeden lub więcej wierszy zlecenia produkcyjnego dla materiału.</span><span class="sxs-lookup"><span data-stu-id="d4df4-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="d4df4-110">Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.</span><span class="sxs-lookup"><span data-stu-id="d4df4-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

> [!NOTE]
> <span data-ttu-id="d4df4-111">Procesy konsygnacji wychodzącej nie są obsługiwane standardowo, a automatyczne arkusze własności nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="d4df4-111">Outbound consignment processes are not supported out-of-the-box and automatic ownership journal processing is not supported.</span></span>

## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="d4df4-112">Tworzenie arkusza własności zapasów</span><span class="sxs-lookup"><span data-stu-id="d4df4-112">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="d4df4-113">Kliknij kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Towary > Zmiana własności zapasów.</span><span class="sxs-lookup"><span data-stu-id="d4df4-113">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="d4df4-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d4df4-114">Click New.</span></span>
    * <span data-ttu-id="d4df4-115">Arkusz zmian własności zapasów służy do zmiany właściciela zapasów konsygnacyjnych z dostawcy na bieżącą firmę.</span><span class="sxs-lookup"><span data-stu-id="d4df4-115">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="d4df4-116">Ta zmiana własności odbywa się poprzez zwolnienie dostępnych zapasów, których właścicielem jest dostawca, a następnie przyjęcie tych zapasów do bieżącej firmy.</span><span class="sxs-lookup"><span data-stu-id="d4df4-116">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="d4df4-117">W polu Nazwa wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d4df4-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="d4df4-118">Można wybrać tylko nazwy arkuszy magazynowych, które mają typ arkusza Zmiana własności.</span><span class="sxs-lookup"><span data-stu-id="d4df4-118">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="d4df4-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d4df4-119">Click OK.</span></span>
5. <span data-ttu-id="d4df4-120">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="d4df4-120">Click Functions.</span></span>
6. <span data-ttu-id="d4df4-121">Kliknij opcję Tworzenie wierszy arkusza na podstawie zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="d4df4-121">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="d4df4-122">W celu rozpoczęcia procesu zmiany własności można wykonać zapytanie do wszystkich wierszy produkcji, które mają zapotrzebowanie na zużycie surowca.</span><span class="sxs-lookup"><span data-stu-id="d4df4-122">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="d4df4-123">W polu Stany wydań z magazynu do uwzględnienia wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d4df4-123">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="d4df4-124">Ta opcja pozwala filtrować według stanu wydania transakcji magazynowych.</span><span class="sxs-lookup"><span data-stu-id="d4df4-124">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="d4df4-125">Na przykład można utworzyć wiersze arkusza dla zapasów, które mają stany fizyczne Pobrane i zarezerwowane.</span><span class="sxs-lookup"><span data-stu-id="d4df4-125">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="d4df4-126">Rozwiń sekcję Rekordy do uwzględnienia.</span><span class="sxs-lookup"><span data-stu-id="d4df4-126">Expand the Records to include section.</span></span>
    * <span data-ttu-id="d4df4-127">Ta sekcja umożliwia zastosowanie dodatkowego filtrowania.</span><span class="sxs-lookup"><span data-stu-id="d4df4-127">This section lets you apply additional filtering.</span></span> <span data-ttu-id="d4df4-128">Na przykład można wybrać datę konkretnego surowca.</span><span class="sxs-lookup"><span data-stu-id="d4df4-128">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="d4df4-129">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d4df4-129">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="d4df4-130">Księgowanie arkusza zmian własności zapasów</span><span class="sxs-lookup"><span data-stu-id="d4df4-130">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="d4df4-131">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="d4df4-131">Click Post.</span></span>
    * <span data-ttu-id="d4df4-132">Podczas księgowania arkusza zapasy będące własnością dostawcy są zwalniane przy użyciu odwołania „Zmiana własności”.</span><span class="sxs-lookup"><span data-stu-id="d4df4-132">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="d4df4-133">Zapasy są następnie przyjmowane jako dostępne przy użyciu transakcji magazynowej, która jest aktualizowana za pomocą przyjęcia produktów z zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="d4df4-133">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="d4df4-134">Należy zauważyć, że są tworzone tylko transakcje związane z zaksięgowanym arkuszem.</span><span class="sxs-lookup"><span data-stu-id="d4df4-134">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="d4df4-135">Nie są tworzone transakcje dla oczekiwanych zapasów.</span><span class="sxs-lookup"><span data-stu-id="d4df4-135">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="d4df4-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d4df4-136">Click OK.</span></span>
3. <span data-ttu-id="d4df4-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d4df4-137">Close the page.</span></span>

