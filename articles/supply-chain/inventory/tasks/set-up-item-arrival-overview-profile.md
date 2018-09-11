--- 
title: "Konfigurowanie profilu przeglądu przyjęć pozycji"
description: "To zadanie koncentruje się na konfiguracji profilu przeglądu przyjęć."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 2f5176ddbf9a28f76b37d20c7b354f3c3939e1e8
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="d2129-103">Konfigurowanie profilu przeglądu przyjęć pozycji</span><span class="sxs-lookup"><span data-stu-id="d2129-103">Set up an item arrival overview profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2129-104">To zadanie koncentruje się na konfiguracji profilu przeglądu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="d2129-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="d2129-105">Profil przeglądu przyjęć to zbiór reguł, które zostaną zastosowane po otwarciu strony Przegląd przyjęć przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d2129-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="d2129-106">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d2129-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="d2129-107">Tę procedurę zazwyczaj wykonuje pracownik przyjmujący.</span><span class="sxs-lookup"><span data-stu-id="d2129-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="d2129-108">Wybierz kolejno opcje Zarządzanie zapasami > Ustawienia > Dystrybucja > Profile przeglądu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="d2129-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="d2129-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d2129-109">Click New.</span></span>
    * <span data-ttu-id="d2129-110">Ponieważ prawie zawsze pracujesz w tym samym magazynie, rozładowując ciężarówki, należy utworzyć profil przeglądu przyjęć, aby uprościć proces rejestrowania przyjętych towarów.</span><span class="sxs-lookup"><span data-stu-id="d2129-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="d2129-111">W polu Nazwa profilu przeglądu przyjęć wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2129-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="d2129-112">W polu Pokaż wiersze wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d2129-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="d2129-113">Wybierz, które wiersze mają być wyświetlane dla przyjęć:   Wszystko — Wyświetlanie wszystkich wierszy, niezależnie od ich stanu.</span><span class="sxs-lookup"><span data-stu-id="d2129-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="d2129-114">W toku — Wyświetlane są wiersze przyjęć, w których postęp ma stan Zakończony lub Częściowo.</span><span class="sxs-lookup"><span data-stu-id="d2129-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="d2129-115">To oznacza, że dla wszystkich wierszy całość lub część ilości została zarejestrowana w arkuszu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="d2129-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="d2129-116">Nieukończone — Wyświetlane są wiersze przyjęć, w których postęp ma stan Brak lub Częściowo.</span><span class="sxs-lookup"><span data-stu-id="d2129-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="d2129-117">To oznacza, że dla wszystkich wierszy zarejestrowana w arkuszu przyjęć została część ilości lub nic nie zostało zarejestrowane.</span><span class="sxs-lookup"><span data-stu-id="d2129-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="d2129-118">Rozwiń lub zwiń sekcję Opcje przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="d2129-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="d2129-119">W polu Dni do przodu wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2129-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="d2129-120">Ustawia to filtr, który pokazuje wiersze przyjęć oczekiwanych do realizacji w ciągu najbliższych kilku dni (w zależności od ustawionej liczby).</span><span class="sxs-lookup"><span data-stu-id="d2129-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="d2129-121">W polu Dni wstecz wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2129-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="d2129-122">Spowoduje to ustawienie filtru wyświetlającego wiersze przyjęć oczekiwanych do realizacji tę liczbę dni przed datą dzisiejszą.</span><span class="sxs-lookup"><span data-stu-id="d2129-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="d2129-123">W polu Magazyny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2129-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="d2129-124">Wyfiltruj jeden lub więcej magazynów.</span><span class="sxs-lookup"><span data-stu-id="d2129-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="d2129-125">W polu Metoda dostawy wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d2129-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="d2129-126">Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tą metodą dostawy.</span><span class="sxs-lookup"><span data-stu-id="d2129-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="d2129-127">W polu Nazwa wybierz wartość WHS.</span><span class="sxs-lookup"><span data-stu-id="d2129-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="d2129-128">W polu Magazyn wybierz magazyn 24.</span><span class="sxs-lookup"><span data-stu-id="d2129-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="d2129-129">Jest to magazyn domyślny, który będzie używany dla zarejestrowanych wierszy przyjęć używających tego profilu.</span><span class="sxs-lookup"><span data-stu-id="d2129-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="d2129-130">W polu Lokalizacja wybierz wartość Baydoor.</span><span class="sxs-lookup"><span data-stu-id="d2129-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="d2129-131">Jest to lokalizacja domyślna, która będzie używana dla zarejestrowanych wierszy przyjęć używających tego profilu.</span><span class="sxs-lookup"><span data-stu-id="d2129-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="d2129-132">Rozwiń lub zwiń sekcję Szczegóły zapytania dotyczącego przyjęcia.</span><span class="sxs-lookup"><span data-stu-id="d2129-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="d2129-133">W polu Ogranicz do oddziału wybierz oddział 2.</span><span class="sxs-lookup"><span data-stu-id="d2129-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="d2129-134">Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tym oddziałem.</span><span class="sxs-lookup"><span data-stu-id="d2129-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="d2129-135">W opcji Zamówienia zakupu ustaw wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="d2129-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="d2129-136">Wybierz wiersze przyjęć z zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="d2129-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="d2129-137">W opcji Zamówienia przeniesienia ustaw wartość Tak.</span><span class="sxs-lookup"><span data-stu-id="d2129-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="d2129-138">Wybierz wiersze przyjęć z zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="d2129-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="d2129-139">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d2129-139">Click Save.</span></span>
18. <span data-ttu-id="d2129-140">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2129-140">Close the page.</span></span>


