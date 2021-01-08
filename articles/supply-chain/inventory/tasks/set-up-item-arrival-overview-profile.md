---
title: Konfigurowanie profilu przeglądu przyjęć pozycji
description: Ten temat koncentruje się na konfiguracji profilu przeglądu przyjęć.
author: ShylaThompson
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69389dd3a53ffec11116e16512bd038b45eda4d4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435481"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="d0899-103">Konfigurowanie profilu przeglądu przyjęć pozycji</span><span class="sxs-lookup"><span data-stu-id="d0899-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="d0899-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="d0899-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="d0899-105">Ten temat koncentruje się na konfiguracji profilu przeglądu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="d0899-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="d0899-106">Profil przeglądu przyjęć to zbiór reguł, które zostaną zastosowane po otwarciu strony Przegląd przyjęć przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0899-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="d0899-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d0899-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="d0899-108">Tę procedurę zazwyczaj wykonuje pracownik przyjmujący.</span><span class="sxs-lookup"><span data-stu-id="d0899-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="d0899-109">Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Dystrybucja > Profile przeglądu przyjęć**.</span><span class="sxs-lookup"><span data-stu-id="d0899-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="d0899-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d0899-110">Select **New**.</span></span> <span data-ttu-id="d0899-111">Ponieważ prawie zawsze pracujesz w tym samym magazynie, rozładowując ciężarówki, należy utworzyć profil przeglądu przyjęć, aby uprościć proces rejestrowania przyjętych towarów.</span><span class="sxs-lookup"><span data-stu-id="d0899-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="d0899-112">W polu **Nazwa profilu przeglądu przyjęć** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0899-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="d0899-113">W polu **Pokaż wiersze** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="d0899-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="d0899-114">Umożliwia wybór wierszy wyświetlanych dla przyjęć:</span><span class="sxs-lookup"><span data-stu-id="d0899-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="d0899-115">**Wszystko** — Wyświetlanie wszystkich wierszy, niezależnie od ich stanu.</span><span class="sxs-lookup"><span data-stu-id="d0899-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="d0899-116">**W toku** — Wyświetlane są wiersze przyjęć, w których postęp ma stan Zakończony lub Częściowo.</span><span class="sxs-lookup"><span data-stu-id="d0899-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="d0899-117">To oznacza, że dla wszystkich wierszy całość lub część ilości została zarejestrowana w arkuszu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="d0899-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="d0899-118">**Nieukończone** — Wyświetlane są wiersze przyjęć, w których postęp ma stan Brak lub Częściowo.</span><span class="sxs-lookup"><span data-stu-id="d0899-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="d0899-119">To oznacza, że dla wszystkich wierszy zarejestrowana w arkuszu przyjęć została część ilości lub nic nie zostało zarejestrowane.</span><span class="sxs-lookup"><span data-stu-id="d0899-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="d0899-120">Rozwiń lub zwiń sekcję **Opcje przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="d0899-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="d0899-121">W polu **Dni do przodu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0899-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="d0899-122">Ustawia to filtr, który pokazuje wiersze przyjęć oczekiwanych do realizacji w ciągu najbliższych kilku dni (w zależności od ustawionej liczby).</span><span class="sxs-lookup"><span data-stu-id="d0899-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="d0899-123">W polu **Dni wstecz** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0899-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="d0899-124">Spowoduje to ustawienie filtru wyświetlającego wiersze przyjęć oczekiwanych do realizacji tę liczbę dni przed datą dzisiejszą.</span><span class="sxs-lookup"><span data-stu-id="d0899-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="d0899-125">W polu **Magazyny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0899-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="d0899-126">Wyfiltruj jeden lub więcej magazynów.</span><span class="sxs-lookup"><span data-stu-id="d0899-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="d0899-127">W polu **Metoda dostawy** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0899-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="d0899-128">Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tą metodą dostawy.</span><span class="sxs-lookup"><span data-stu-id="d0899-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="d0899-129">W polu **Nazwa** wybierz wartość WHS.</span><span class="sxs-lookup"><span data-stu-id="d0899-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="d0899-130">W polu **Magazyn** wybierz magazyn 24.</span><span class="sxs-lookup"><span data-stu-id="d0899-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="d0899-131">Jest to magazyn domyślny, który będzie używany dla zarejestrowanych wierszy przyjęć używających tego profilu.</span><span class="sxs-lookup"><span data-stu-id="d0899-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="d0899-132">W polu **Lokalizacja** wybierz wartość **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="d0899-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="d0899-133">Jest to lokalizacja domyślna, która będzie używana dla zarejestrowanych wierszy przyjęć używających tego profilu.</span><span class="sxs-lookup"><span data-stu-id="d0899-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="d0899-134">Rozwiń lub zwiń sekcję **Szczegóły zapytania dotyczącego przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="d0899-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="d0899-135">W polu **Ogranicz do oddziału** wybierz oddział 2.</span><span class="sxs-lookup"><span data-stu-id="d0899-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="d0899-136">Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tym oddziałem.</span><span class="sxs-lookup"><span data-stu-id="d0899-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="d0899-137">W opcji **Zamówienia zakupu** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d0899-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="d0899-138">Wybierz wiersze przyjęć z zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="d0899-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="d0899-139">W opcji Zamówienia **przeniesienia** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d0899-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="d0899-140">Wybierz wiersze przyjęć z zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="d0899-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="d0899-141">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d0899-141">Select **Save**.</span></span>
18. <span data-ttu-id="d0899-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d0899-142">Close the page.</span></span>

