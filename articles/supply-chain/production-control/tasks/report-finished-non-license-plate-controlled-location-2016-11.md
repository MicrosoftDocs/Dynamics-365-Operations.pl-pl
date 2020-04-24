---
title: Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez numer identyfikacyjny (zgłoszenie, maj 2016)
description: Ten przewodnik po zadaniach zawiera przykład zgłaszania wyrobu gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a9010b95cfd0528cd3b532627d19a3b340bdca4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210578"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a><span data-ttu-id="6e1ae-103">Zgłaszanie wyrobów gotowych do lokalizacji niekontrolowanej przez numer identyfikacyjny (zgłoszenie, maj 2016)</span><span class="sxs-lookup"><span data-stu-id="6e1ae-103">Report as finished to a non-license plate controlled location  (Application, May 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6e1ae-104">Ten przewodnik po zadaniach zawiera przykład zgłaszania wyrobu gotowego do lokalizacji, która nie jest kontrolowana przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-104">This task guide shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="6e1ae-105">Warunkiem wstępnym tego zadania jest istnienie odpowiedniej zasady pracy.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-105">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="6e1ae-106">Poprzedni przewodnik po zadaniach pokazywał konfigurację zasady pracy.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-106">A previous task guide showed the setup of the work policy.</span></span> <span data-ttu-id="6e1ae-107">Ten przewodnik po zadaniach wymaga aplikacji Dynamics AX w wersji 7.0.1 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>




## <a name="set-up-an-output-location"></a><span data-ttu-id="6e1ae-108">Konfigurowanie lokalizacji wyjściowej</span><span class="sxs-lookup"><span data-stu-id="6e1ae-108">Set up an output location</span></span>
1. <span data-ttu-id="6e1ae-109">Wybierz kolejno opcje Administrowanie organizacją > Zasoby > Grupy zasobów.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-109">Go to Organization administration > Resources > Resource groups.</span></span>
2. <span data-ttu-id="6e1ae-110">Na liście zaznacz grupę zasobów „5102”.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-110">In the list, select resource group '5102'.</span></span>
3. <span data-ttu-id="6e1ae-111">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-111">Click Edit.</span></span>
4. <span data-ttu-id="6e1ae-112">W polu Magazyn wyjściowy wpisz „51”.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-112">In the Output warehouse field, enter '51'.</span></span>
5. <span data-ttu-id="6e1ae-113">W polu Lokalizacja wyjściowa wpisz „001”.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-113">In the Output location field, enter '001'.</span></span>
    * <span data-ttu-id="6e1ae-114">Lokalizacja 001 nie jest lokalizacją kontrolowaną przez numer identyfikacyjny.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-114">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="6e1ae-115">Można skonfigurować lokalizację wyjściową niekontrolowaną za pomocą numeru identyfikacyjnego, ale tylko wtedy, gdy istnieje odpowiednia zasada pracy dla lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-115">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span>  

## <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="6e1ae-116">Tworzenie zlecenia produkcyjnego i zgłaszanie go jako gotowego</span><span class="sxs-lookup"><span data-stu-id="6e1ae-116">Create a production order and report it as finished</span></span>
1. <span data-ttu-id="6e1ae-117">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-117">Close the page.</span></span>
2. <span data-ttu-id="6e1ae-118">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-118">Go to Production control > Production orders > All production orders.</span></span>
3. <span data-ttu-id="6e1ae-119">Kliknij opcję Nowe zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-119">Click New production order.</span></span>
4. <span data-ttu-id="6e1ae-120">W polu Numer pozycji wpisz „L0101”.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-120">In the Item number field, enter 'L0101'.</span></span>
5. <span data-ttu-id="6e1ae-121">Kliknij Utwórz.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-121">Click Create.</span></span>
6. <span data-ttu-id="6e1ae-122">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-122">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="6e1ae-123">Kliknij przycisk Szacuj.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-123">Click Estimate.</span></span>
8. <span data-ttu-id="6e1ae-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-124">Click OK.</span></span>
9. <span data-ttu-id="6e1ae-125">Kliknij przycisk Uruchom.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-125">Click Start.</span></span>
10. <span data-ttu-id="6e1ae-126">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-126">Click the General tab.</span></span>
11. <span data-ttu-id="6e1ae-127">W polu Automatyczne zużycie BOM zaznacz opcję „Nigdy”.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-127">In the Automatic BOM consumption field, select 'Never'.</span></span>
12. <span data-ttu-id="6e1ae-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-128">Click OK.</span></span>
13. <span data-ttu-id="6e1ae-129">Kliknij opcję Zgłoś jako gotowe.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-129">Click Report as finished.</span></span>
14. <span data-ttu-id="6e1ae-130">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-130">Click the General tab.</span></span>
15. <span data-ttu-id="6e1ae-131">W polu Akceptacja błędu wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-131">Select Yes in the Accept error field.</span></span>
16. <span data-ttu-id="6e1ae-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-132">Click OK.</span></span>
17. <span data-ttu-id="6e1ae-133">W okienku akcji kliknij pozycję Magazyn.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-133">On the Action Pane, click Warehouse.</span></span>
18. <span data-ttu-id="6e1ae-134">Kliknij opcję Szczegóły pracy.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-134">Click Work details.</span></span>
    * <span data-ttu-id="6e1ae-135">Po zgłoszeniu zlecenia produkcyjnego jako gotowego nie została wygenerowana żadna praca odłożenia.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-135">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="6e1ae-136">Dzieje się tak, ponieważ zdefiniowano zasadę pracy, która blokuje generowanie pracy, gdy produkt L0101 jest zgłaszany jako gotowy do lokalizacji 001.</span><span class="sxs-lookup"><span data-stu-id="6e1ae-136">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span>  

