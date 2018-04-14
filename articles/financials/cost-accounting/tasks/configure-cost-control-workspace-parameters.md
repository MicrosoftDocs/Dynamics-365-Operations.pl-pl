--- 
title: "Konfigurowanie parametrów obszaru roboczego kontroli kosztów"
description: "Ta procedura służy do konfigurowania obszaru roboczego Kontrola kosztów, tak aby kierownicy na różnych poziomach w organizacji mogli uzyskać wgląd w podległe im obiekty kosztów, takie jak centra kosztów i grupy produktów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1d2448642b0f60f8c060b3fd3e04b22e269814d4
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="configure-cost-control-workspace-parameters"></a><span data-ttu-id="24807-103">Konfigurowanie parametrów obszaru roboczego kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="24807-103">Configure cost control workspace parameters</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="24807-104">Ta procedura służy do konfigurowania obszaru roboczego Kontrola kosztów, tak aby kierownicy na różnych poziomach w organizacji mogli uzyskać wgląd w podległe im obiekty kosztów, takie jak centra kosztów i grupy produktów.</span><span class="sxs-lookup"><span data-stu-id="24807-104">Use this procedure to configure the Cost control workspace so that managers at various levels in an organization can gain insight into their cost objects, such as cost centers and product groups.</span></span> <span data-ttu-id="24807-105">Do utworzenia tego nagrania użyto firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="24807-105">The USP2 demo company was used to create this recording.</span></span>

1. <span data-ttu-id="24807-106">Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Konfiguracja obszaru roboczego Kontrola kosztów.</span><span class="sxs-lookup"><span data-stu-id="24807-106">Go to Cost accounting > Setup > Cost control workspace configuration.</span></span>
2. <span data-ttu-id="24807-107">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="24807-107">Click New.</span></span>
3. <span data-ttu-id="24807-108">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-108">In the Name field, type a value.</span></span>
4. <span data-ttu-id="24807-109">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="24807-109">In the Description field, type a value.</span></span>
5. <span data-ttu-id="24807-110">W polu Opublikowane wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24807-110">Select Yes in the Published field.</span></span>
    * <span data-ttu-id="24807-111">Jeśli w tej opcji ustawisz wartość Tak, raporty w obszarze roboczym Kontrola kosztów będą mogły być wyświetlane przez użytkowników przypisanych do jednej z następujących ról: Menedżer rachunku kosztów, Księgowy kosztów, Księgowy rachunku kosztów lub Kontroler obiektów kosztów.</span><span class="sxs-lookup"><span data-stu-id="24807-111">If you set this option to Yes, users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, cost accountant clerk, or cost object controller.</span></span> <span data-ttu-id="24807-112">Jeśli w tej opcji ustawisz wartość Nie, raporty w obszarze roboczym Kontrola kosztów będą mogły być wyświetlane przez użytkowników przypisanych do jednej z następujących ról: Menedżer rachunku kosztów, Księgowy kosztów lub Księgowy rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="24807-112">If you set this option to No, only users who are assigned one of these roles can see the report in the Cost control workspace: cost accounting manager, cost accountant, or cost accountant clerk.</span></span>  
6. <span data-ttu-id="24807-113">Rozwiń sekcję Filtrowanie danych.</span><span class="sxs-lookup"><span data-stu-id="24807-113">Expand the Data filtering section.</span></span>
7. <span data-ttu-id="24807-114">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-114">In the Cost control unit field, enter or select a value.</span></span>
8. <span data-ttu-id="24807-115">W polu Pierwotna wersja budżetu wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-115">In the Budget original version field, enter or select a value.</span></span>
9. <span data-ttu-id="24807-116">W polu Hierarchia wymiarów składników kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-116">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
10. <span data-ttu-id="24807-117">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-117">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
11. <span data-ttu-id="24807-118">Rozwiń sekcję Przypisz rekordy obliczeń.</span><span class="sxs-lookup"><span data-stu-id="24807-118">Expand the Assign calculation records section.</span></span>
12. <span data-ttu-id="24807-119">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="24807-119">Click New.</span></span>
13. <span data-ttu-id="24807-120">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="24807-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="24807-121">W polu Okres kalendarza obrachunkowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-121">In the Fiscal calendar period field, enter or select a value.</span></span>
15. <span data-ttu-id="24807-122">W polu Wersja rzeczywista wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-122">In the Actual version field, enter or select a value.</span></span>
16. <span data-ttu-id="24807-123">Rozwiń sekcję Okresy obrachunkowe na kolumnę.</span><span class="sxs-lookup"><span data-stu-id="24807-123">Expand the Fiscal periods per column section.</span></span>
17. <span data-ttu-id="24807-124">W polu Bieżący okres zaznacz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24807-124">Select Yes in the Current period field.</span></span>
18. <span data-ttu-id="24807-125">Rozwiń sekcję Kolumny do wyświetlenia dla kosztów.</span><span class="sxs-lookup"><span data-stu-id="24807-125">Expand the Columns to display for costs section.</span></span>
19. <span data-ttu-id="24807-126">W polu Koszt stały wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24807-126">Select Yes in the Fixed cost field.</span></span>
20. <span data-ttu-id="24807-127">W polu Koszt zmienny wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24807-127">Select Yes in the Variable cost field.</span></span>
21. <span data-ttu-id="24807-128">W polu Łączny koszt wybierz opcję Tak.</span><span class="sxs-lookup"><span data-stu-id="24807-128">Select Yes in the Total cost field.</span></span>
22. <span data-ttu-id="24807-129">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="24807-129">Click Save.</span></span>
23. <span data-ttu-id="24807-130">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="24807-130">Close the page.</span></span>
24. <span data-ttu-id="24807-131">Wybierz kolejno opcje Rachunek kosztów > Obszary robocze > Kontrola kosztów.</span><span class="sxs-lookup"><span data-stu-id="24807-131">Go to Cost accounting > Workspaces > Cost control.</span></span>
25. <span data-ttu-id="24807-132">Wybierz zestawienie, aby wyświetlić koszty stałe, zmienne, łączne i nieklasyfikowane dla wybranych okresów obrachunkowych.</span><span class="sxs-lookup"><span data-stu-id="24807-132">Select a statement to see fixed, variable, total, and unclassified costs for the selected fiscal periods.</span></span>
26. <span data-ttu-id="24807-133">W polu Okres kalendarza obrachunkowego wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-133">In the Fiscal calendar period field, enter or select a value.</span></span>
27. <span data-ttu-id="24807-134">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-134">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="24807-135">Po wybraniu hierarchii wymiarów obiektów kosztów rozwiń hierarchię wymiarów składników kosztów, aby zobaczyć żądane wartości kosztów.</span><span class="sxs-lookup"><span data-stu-id="24807-135">After you've selected a Cost object dimension hierarchy, expand the Cost element dimension hierarchy to see the desired cost values.</span></span> <span data-ttu-id="24807-136">Na przykład po rozwinięciu hierarchii do poziomu Koszty ogólne produkcji można zobaczyć wartość.</span><span class="sxs-lookup"><span data-stu-id="24807-136">For example, you can expand the hierarchy to Manufacturing overhead to see the value.</span></span>  


