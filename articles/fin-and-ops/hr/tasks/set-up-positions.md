---
title: Konfigurowanie stanowisk
description: Pozycje są ważnym elementem dla niższego poziomu hierarchii organizacji.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, HcmWorkforceWorkspace, HcmWorkerActivityChart, HcmAllWorkersListPart, HcmPosition, HcmPositionNewPosition, HcmJobLookup, HcmPositionReportsToDialog, HcmPositionLookup, FinancialDimensionDefaultTemplatesLookup, DimensionLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4fd355fb6c3d2742e046a616585ca349c623341d
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "856837"
---
# <a name="set-up-positions"></a><span data-ttu-id="76920-103">Konfigurowanie stanowisk</span><span class="sxs-lookup"><span data-stu-id="76920-103">Set up positions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76920-104">Pozycje są ważnym elementem dla niższego poziomu hierarchii organizacji.</span><span class="sxs-lookup"><span data-stu-id="76920-104">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="76920-105">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="76920-105">A position is an individual instance of a job.</span></span> <span data-ttu-id="76920-106">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z zadaniem „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="76920-106">For example, the position, “Sales manager (East),” is one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="76920-107">Stanowisko istnieje w dziale i może być z nim powiązany tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="76920-107">A position exists in a department and may have only one worker associated with it.</span></span> <span data-ttu-id="76920-108">W tym zadaniu pokażemy kroki wymagane do utworzenia stanowiska.</span><span class="sxs-lookup"><span data-stu-id="76920-108">In this task we will walk through the steps required to create a position.</span></span> <span data-ttu-id="76920-109">Ta procedura jest przeznaczona dla specjalistów ds. zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="76920-109">This procedure is intended for Human Resources Specialists.</span></span>

1. <span data-ttu-id="76920-110">Kliknij przycisk Zarządzanie pracownikami.</span><span class="sxs-lookup"><span data-stu-id="76920-110">Click Workforce management.</span></span>
2. <span data-ttu-id="76920-111">Kliknij opcję Otwórz stanowiska.</span><span class="sxs-lookup"><span data-stu-id="76920-111">Click Open positions.</span></span>
3. <span data-ttu-id="76920-112">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="76920-112">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="76920-113">W polu Zadanie wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-113">In the Job field, enter or select a value.</span></span>
    * <span data-ttu-id="76920-114">Opis zadania, tytuł i współczynnik zatrudnienia w postaci równoważnika pełnego etatu zostaną skopiowane z wybranego zadania do stanowiska.</span><span class="sxs-lookup"><span data-stu-id="76920-114">The Job description, title, and full-time equivalent employment factor are automatically copied from the selected job into the position.</span></span>  
5. <span data-ttu-id="76920-115">Rozstrzygnij zmiany w zadaniu.</span><span class="sxs-lookup"><span data-stu-id="76920-115">ResolveChanges the Job.</span></span>
6. <span data-ttu-id="76920-116">Kliknij przycisk Utwórz stanowisko.</span><span class="sxs-lookup"><span data-stu-id="76920-116">Click Create position.</span></span>
7. <span data-ttu-id="76920-117">W polu Dział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-117">In the Department field, enter or select a value.</span></span>
8. <span data-ttu-id="76920-118">W polu Typ stanowiska wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-118">In the Position type field, enter or select a value.</span></span>
9. <span data-ttu-id="76920-119">W polu Region wynagrodzenia wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-119">In the Compensation region field, enter or select a value.</span></span>
    * <span data-ttu-id="76920-120">Pole Region wynagrodzenia decyduje o regułach uprawnień do wynagrodzenia i budżetach stałych podwyżek, które mają zastosowanie do pracownika na tym stanowisku.</span><span class="sxs-lookup"><span data-stu-id="76920-120">The Compensation region field determines the compensation eligibility rules and fixed increase budgets that apply to an employee in that position.</span></span>  
10. <span data-ttu-id="76920-121">W polu Dostępne do przypisania wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="76920-121">In the Available for assignment field, enter a date and time.</span></span>
11. <span data-ttu-id="76920-122">Rozwiń sekcję Okres ważności stanowiska.</span><span class="sxs-lookup"><span data-stu-id="76920-122">Expand the Position duration section.</span></span>
    * <span data-ttu-id="76920-123">Okres ważności stanowiska jest wprowadzany domyślnie na podstawie wcześniej wprowadzonych dat aktywacji i likwidacji.</span><span class="sxs-lookup"><span data-stu-id="76920-123">Position duration is entered by default based on activation and retirement dates entered earlier</span></span>  
12. <span data-ttu-id="76920-124">Rozwiń sekcję Stanowisko zwierzchnie.</span><span class="sxs-lookup"><span data-stu-id="76920-124">Expand the Reports to position section.</span></span>
    * <span data-ttu-id="76920-125">Podczas przypisywania pracownika do stanowiska podrzędnego względem innego stanowiska tworzy się relacja bezpośredniej zwierzchności między pracownikami przypisanymi do tych dwóch stanowisk.</span><span class="sxs-lookup"><span data-stu-id="76920-125">When you assign a worker to a position that reports to another position, you create a direct reporting relationship between the workers who are assigned to the two positions.</span></span>  
13. <span data-ttu-id="76920-126">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="76920-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="76920-127">W polu Przełożony wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-127">In the Reports to field, enter or select a value.</span></span>
15. <span data-ttu-id="76920-128">Kliknij Utwórz.</span><span class="sxs-lookup"><span data-stu-id="76920-128">Click Create.</span></span>
16. <span data-ttu-id="76920-129">Rozwiń sekcję Przypisanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="76920-129">Expand the Worker assignment section.</span></span>
17. <span data-ttu-id="76920-130">Rozwiń sekcję Relacje.</span><span class="sxs-lookup"><span data-stu-id="76920-130">Expand the Relationships section.</span></span>
    * <span data-ttu-id="76920-131">Jeśli organizacja korzysta z hierarchii macierzy lub innej hierarchii niestandardowej, można ustawić typy hierarchii pozycji i dodawać relacje raportowania do pozycji dla każdego konfigurowanego typu hierarchii.</span><span class="sxs-lookup"><span data-stu-id="76920-131">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span>  
18. <span data-ttu-id="76920-132">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="76920-132">Click Add.</span></span>
19. <span data-ttu-id="76920-133">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="76920-133">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="76920-134">W polu Nazwa hierarchii wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-134">In the Hierarchy name field, enter or select a value.</span></span>
21. <span data-ttu-id="76920-135">W polu Stanowisko zwierzchnie wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-135">In the Reports to position field, enter or select a value.</span></span>
22. <span data-ttu-id="76920-136">Rozwiń sekcję Lista płac.</span><span class="sxs-lookup"><span data-stu-id="76920-136">Expand the Payroll section.</span></span>
23. <span data-ttu-id="76920-137">W polu Cykl płac wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-137">In the Pay cycle field, enter or select a value.</span></span>
24. <span data-ttu-id="76920-138">W polu Zapłacone przez wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-138">In the Paid by field, enter or select a value.</span></span>
25. <span data-ttu-id="76920-139">W polu Zwykłe godziny (rocznie) wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="76920-139">In the Annual regular hours field, enter a number.</span></span>
    * <span data-ttu-id="76920-140">To jest liczba regularnie płatnych godzin, jaką oczekuje się, że pracownik na tym stanowisku przepracuje w każdym roku.</span><span class="sxs-lookup"><span data-stu-id="76920-140">This is the number of regularly paid hours that the worker in this position is expected to work each year.</span></span>  
26. <span data-ttu-id="76920-141">Rozwiń sekcję Związek zawodowy.</span><span class="sxs-lookup"><span data-stu-id="76920-141">Expand the Labor union section.</span></span>
27. <span data-ttu-id="76920-142">Zwiń sekcję Związek zawodowy.</span><span class="sxs-lookup"><span data-stu-id="76920-142">Collapse the Labor union section.</span></span>
28. <span data-ttu-id="76920-143">Rozwiń sekcję Wymiary finansowe.</span><span class="sxs-lookup"><span data-stu-id="76920-143">Expand the Financial dimensions section.</span></span>
29. <span data-ttu-id="76920-144">W polu Szablon dystrybucji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-144">In the Distribution template field, enter or select a value.</span></span>
30. <span data-ttu-id="76920-145">W polu Dział wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="76920-145">In the Department field, enter or select a value.</span></span>
31. <span data-ttu-id="76920-146">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="76920-146">Click Save.</span></span>

