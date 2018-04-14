--- 
title: Wprowadzanie kart czasu pracy projektu
description: "Ta procedura pozwala tworzyć karty czasu pracy, używając pustego formularza karty czasu pracy."
author: kherr75
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.search.industry: Service industries
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fdc9567040a2ea4e50325c98a2da19da039586bb
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="enter-project-timesheets"></a><span data-ttu-id="7a8c7-103">Wprowadzanie kart czasu pracy projektu</span><span class="sxs-lookup"><span data-stu-id="7a8c7-103">Enter project timesheets</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a8c7-104">Ta procedura pozwala tworzyć karty czasu pracy, używając pustego formularza karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="7a8c7-105">Nowa karta czasu pracy może się opierać na informacjach z poprzedniej karty czasu pracy lub z projektów i działań przypisanych na stronie Moje ulubione.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the My favorites page.</span></span> <span data-ttu-id="7a8c7-106">Domyślnie strona listy Wszystkie karty czasu pracy wyświetla wszystkie karty czasu pracy dla bieżącego okresu.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-106">By default, the All timesheets list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="7a8c7-107">Można użyć listy rozwijanej pola Pokaż znajdującego się na stronie Moje karty czasu pracy, aby wyfiltrować listę kart czasu pracy według okresu lub projektu lub wyświetlić grafiki utworzone w imieniu innych pracowników.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-107">You can use the drop-down list for the Show field in the My timesheets page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="7a8c7-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USSI.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-108">The demo data company used to create this procedure is USSI.</span></span> <span data-ttu-id="7a8c7-109">Aby rozpocząć tę procedurę, wybierz kolejno opcje Zarządzanie projektami i ich księgowanie > Karty czasu pracy > Moje karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-109">To begin this procedure, go to Project management and accounting > Timesheets >My timesheets</span></span>

1. <span data-ttu-id="7a8c7-110">Aby wprowadzić nową kartę czasu pracy, kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-110">To enter a new timesheet, click New.</span></span>
    * <span data-ttu-id="7a8c7-111">Lista rozwijana Zasób domyślnie zawiera pracownika przypisanego do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    * <span data-ttu-id="7a8c7-112">Jeśli użytkownik jest oznaczony jako pełnomocnik, zostanie wyświetlona lista imion i nazwisk, dzięki czemu użytkownik może wprowadzić kartę czasu pracy w imieniu tych osób.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
2. <span data-ttu-id="7a8c7-113">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-113">In the Date field, enter a date.</span></span>
    * <span data-ttu-id="7a8c7-114">Jeśli ta opcja jest zaznaczona, nowe wiersze karty czasu pracy zostaną utworzone przy użyciu ustawień karty czasu pracy skonfigurowanych jako ulubione.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
3. <span data-ttu-id="7a8c7-115">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-115">Click OK.</span></span>
4. <span data-ttu-id="7a8c7-116">Kliknij opcję Nowy wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-116">Click New line.</span></span>
5. <span data-ttu-id="7a8c7-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="7a8c7-118">W polu Firma jest domyślnie wyświetlana bieżąca firma.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-118">The Legal Entity field displays the current Legal entity by default.</span></span>   
6. <span data-ttu-id="7a8c7-119">W polu Projekt kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-119">In the Project field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7a8c7-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-120">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="7a8c7-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-121">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7a8c7-122">W polu Działanie kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-122">In the Activity field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="7a8c7-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-123">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="7a8c7-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-124">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="7a8c7-125">W polu Kategoria kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-125">In the Category field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="7a8c7-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-126">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="7a8c7-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-127">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="7a8c7-128">Wprowadź liczbę godzin przepracowanych każdego dnia.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-128">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="7a8c7-129">Godziny należy wprowadzić w formacie dziesiętnym.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-129">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="7a8c7-130">Na przykład, jeśli użytkownik pracował przez dwie godziny i piętnaście minut, wprowadź 2.25.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
16. <span data-ttu-id="7a8c7-131">Wprowadź liczbę godzin przepracowanych każdego dnia.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-131">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="7a8c7-132">Godziny należy wprowadzić w formacie dziesiętnym.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-132">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="7a8c7-133">Na przykład, jeśli użytkownik pracował przez dwie godziny i piętnaście minut, wprowadź 2.25.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-133">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="7a8c7-134">Wprowadź liczbę godzin przepracowanych każdego dnia.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-134">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="7a8c7-135">Godziny należy wprowadzić w formacie dziesiętnym.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-135">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="7a8c7-136">Na przykład, jeśli użytkownik pracował przez dwie godziny i piętnaście minut, wprowadź 2.25.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-136">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
18. <span data-ttu-id="7a8c7-137">Wprowadź liczbę godzin przepracowanych każdego dnia.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-137">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="7a8c7-138">Godziny należy wprowadzić w formacie dziesiętnym.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-138">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="7a8c7-139">Na przykład, jeśli użytkownik pracował przez dwie godziny i piętnaście minut, wprowadź 2.25.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-139">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
19. <span data-ttu-id="7a8c7-140">Wprowadź liczbę godzin przepracowanych każdego dnia.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-140">Enter the number of hours worked each day.</span></span>
    * <span data-ttu-id="7a8c7-141">Godziny należy wprowadzić w formacie dziesiętnym.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-141">Hours should be entered in a decimal format.</span></span>  <span data-ttu-id="7a8c7-142">Na przykład, jeśli użytkownik pracował przez dwie godziny i piętnaście minut, wprowadź 2.25.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-142">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
    * <span data-ttu-id="7a8c7-143">W polu Szczegóły wiersza są dostępne następujące opcje:  o  Dodawanie informacji dotyczących podatków i wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-143">In Line details, the following options are available:  o  Add information about taxes and financial dimensions.</span></span>  <span data-ttu-id="7a8c7-144">o    Dodawanie komentarzy dotyczących wiersza karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-144">o    Add comments about the timesheet line.</span></span>  
20. <span data-ttu-id="7a8c7-145">Kliknij opcję Przepływ pracy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-145">Click Workflow to open the drop dialog.</span></span>
21. <span data-ttu-id="7a8c7-146">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-146">Click Submit.</span></span>
22. <span data-ttu-id="7a8c7-147">Kliknij przycisk Prześlij.</span><span class="sxs-lookup"><span data-stu-id="7a8c7-147">Click Submit.</span></span>


