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
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ecfe132d9b0e096c5fdf015f80a6efb34c9b178
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961443"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="0a379-103">Konfigurowanie profilu przeglądu przyjęć pozycji</span><span class="sxs-lookup"><span data-stu-id="0a379-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="0a379-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="0a379-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="0a379-105">Ten temat koncentruje się na konfiguracji profilu przeglądu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="0a379-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="0a379-106">Profil przeglądu przyjęć to zbiór reguł, które zostaną zastosowane po otwarciu strony Przegląd przyjęć przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0a379-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="0a379-107">Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0a379-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="0a379-108">Tę procedurę zazwyczaj wykonuje pracownik przyjmujący.</span><span class="sxs-lookup"><span data-stu-id="0a379-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="0a379-109">Otwórz w okienku nawigacji **Moduły > Zarządzanie zapasami > Ustawienia > Dystrybucja > Profile przeglądu przyjęć**.</span><span class="sxs-lookup"><span data-stu-id="0a379-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="0a379-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0a379-110">Select **New**.</span></span> <span data-ttu-id="0a379-111">Ponieważ prawie zawsze pracujesz w tym samym magazynie, rozładowując ciężarówki, należy utworzyć profil przeglądu przyjęć, aby uprościć proces rejestrowania przyjętych towarów.</span><span class="sxs-lookup"><span data-stu-id="0a379-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="0a379-112">W polu **Nazwa profilu przeglądu przyjęć** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a379-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="0a379-113">W polu **Pokaż wiersze** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="0a379-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="0a379-114">Umożliwia wybór wierszy wyświetlanych dla przyjęć:</span><span class="sxs-lookup"><span data-stu-id="0a379-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="0a379-115">**Wszystko** — Wyświetlanie wszystkich wierszy, niezależnie od ich stanu.</span><span class="sxs-lookup"><span data-stu-id="0a379-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="0a379-116">**W toku** — Wyświetlane są wiersze przyjęć, w których postęp ma stan Zakończony lub Częściowo.</span><span class="sxs-lookup"><span data-stu-id="0a379-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="0a379-117">To oznacza, że dla wszystkich wierszy całość lub część ilości została zarejestrowana w arkuszu przyjęć.</span><span class="sxs-lookup"><span data-stu-id="0a379-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="0a379-118">**Nieukończone** — Wyświetlane są wiersze przyjęć, w których postęp ma stan Brak lub Częściowo.</span><span class="sxs-lookup"><span data-stu-id="0a379-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="0a379-119">To oznacza, że dla wszystkich wierszy zarejestrowana w arkuszu przyjęć została część ilości lub nic nie zostało zarejestrowane.</span><span class="sxs-lookup"><span data-stu-id="0a379-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="0a379-120">Rozwiń lub zwiń sekcję **Opcje przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="0a379-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="0a379-121">W polu **Dni do przodu** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a379-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="0a379-122">Ustawia to filtr, który pokazuje wiersze przyjęć oczekiwanych do realizacji w ciągu najbliższych kilku dni (w zależności od ustawionej liczby).</span><span class="sxs-lookup"><span data-stu-id="0a379-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="0a379-123">W polu **Dni wstecz** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a379-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="0a379-124">Spowoduje to ustawienie filtru wyświetlającego wiersze przyjęć oczekiwanych do realizacji tę liczbę dni przed datą dzisiejszą.</span><span class="sxs-lookup"><span data-stu-id="0a379-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="0a379-125">W polu **Magazyny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a379-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="0a379-126">Wyfiltruj jeden lub więcej magazynów.</span><span class="sxs-lookup"><span data-stu-id="0a379-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="0a379-127">W polu **Metoda dostawy** wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="0a379-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="0a379-128">Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tą metodą dostawy.</span><span class="sxs-lookup"><span data-stu-id="0a379-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="0a379-129">W polu **Nazwa** wybierz wartość WHS.</span><span class="sxs-lookup"><span data-stu-id="0a379-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="0a379-130">W polu **Magazyn** wybierz magazyn 24.</span><span class="sxs-lookup"><span data-stu-id="0a379-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="0a379-131">Jest to magazyn domyślny, który będzie używany dla zarejestrowanych wierszy przyjęć używających tego profilu.</span><span class="sxs-lookup"><span data-stu-id="0a379-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="0a379-132">W polu **Lokalizacja** wybierz wartość **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="0a379-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="0a379-133">Jest to lokalizacja domyślna, która będzie używana dla zarejestrowanych wierszy przyjęć używających tego profilu.</span><span class="sxs-lookup"><span data-stu-id="0a379-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="0a379-134">Rozwiń lub zwiń sekcję **Szczegóły zapytania dotyczącego przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="0a379-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="0a379-135">W polu **Ogranicz do oddziału** wybierz oddział 2.</span><span class="sxs-lookup"><span data-stu-id="0a379-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="0a379-136">Spowoduje to ustawienie filtru wyświetlającego tylko wiersze przyjęć z tym oddziałem.</span><span class="sxs-lookup"><span data-stu-id="0a379-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="0a379-137">W opcji **Zamówienia zakupu** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0a379-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="0a379-138">Wybierz wiersze przyjęć z zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="0a379-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="0a379-139">W opcji Zamówienia **przeniesienia** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0a379-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="0a379-140">Wybierz wiersze przyjęć z zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="0a379-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="0a379-141">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0a379-141">Select **Save**.</span></span>
18. <span data-ttu-id="0a379-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0a379-142">Close the page.</span></span>

