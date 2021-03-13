---
title: Wprowadzanie kart czasu pracy projektu
description: Ta procedura pozwala tworzyć karty czasu pracy, używając pustego formularza karty czasu pracy.
author: andreabichsel
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.search.industry: Service industries
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4a600137fc583aef8c85c920ca3cd2949a1a19d
ms.sourcegitcommit: 0cca2f82ae5c91c409e2abbf5867ff4e59ba71d6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2021
ms.locfileid: "5055946"
---
# <a name="enter-project-timesheets"></a><span data-ttu-id="a402a-103">Wprowadzanie kart czasu pracy projektu</span><span class="sxs-lookup"><span data-stu-id="a402a-103">Enter project timesheets</span></span>

<span data-ttu-id="a402a-104">Ta procedura pozwala tworzyć karty czasu pracy, używając pustego formularza karty czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="a402a-104">This procedure lets you create a timesheet by using an empty timesheet form.</span></span> <span data-ttu-id="a402a-105">Nowa karta czasu pracy może się opierać na informacjach z poprzedniej karty czasu pracy lub z projektów i działań przypisanych na stronie **Moje ulubione**.</span><span class="sxs-lookup"><span data-stu-id="a402a-105">The new timesheet can be based on information from a previous timesheet, or from project and activity assignments in the **My favorites** page.</span></span> <span data-ttu-id="a402a-106">Domyślnie strona listy **Wszystkie karty** czasu pracy wyświetla wszystkie karty czasu pracy dla bieżącego okresu.</span><span class="sxs-lookup"><span data-stu-id="a402a-106">By default, the **All timesheets** list page displays all your timesheets for the current period.</span></span> <span data-ttu-id="a402a-107">Można użyć listy rozwijanej pola **Pokaż** znajdującego się na stronie **Moje karty czasu pracy**, aby wyfiltrować listę kart czasu pracy według okresu lub projektu lub wyświetlić grafiki utworzone w imieniu innych pracowników.</span><span class="sxs-lookup"><span data-stu-id="a402a-107">You can use the drop-down list for the **Show** field in the **My timesheets** page to filter the timesheet list by time period or project, or to view timesheets that were created on behalf of other workers.</span></span> <span data-ttu-id="a402a-108">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USSI.</span><span class="sxs-lookup"><span data-stu-id="a402a-108">The demo data company used to create this procedure is USSI.</span></span>  

1. <span data-ttu-id="a402a-109">W **okienku nawigacji** przejdź do **Moduły > Zarządzanie projektami i ich księgowanie > Karty czasu pracy > Wszystkie karty czasu pracy**.</span><span class="sxs-lookup"><span data-stu-id="a402a-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Timesheets > My timesheets**.</span></span>
2. <span data-ttu-id="a402a-110">Aby wprowadzić nową kartę czasu pracy, kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a402a-110">To enter a new timesheet, click **New**.</span></span>
    - <span data-ttu-id="a402a-111">Lista rozwijana Zasób domyślnie zawiera pracownika przypisanego do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a402a-111">The Resource drop-down list shows the worker assigned to the current user, by default.</span></span>  
    - <span data-ttu-id="a402a-112">Jeśli użytkownik jest oznaczony jako pełnomocnik, zostanie wyświetlona lista imion i nazwisk, dzięki czemu użytkownik może wprowadzić kartę czasu pracy w imieniu tych osób.</span><span class="sxs-lookup"><span data-stu-id="a402a-112">If the user is designated as a delegate, this will list the names so that a user can enter a timesheet on their behalf.</span></span>  
3. <span data-ttu-id="a402a-113">W polu **Data** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="a402a-113">In the **Date** field, enter a date.</span></span> <span data-ttu-id="a402a-114">Jeśli ta opcja jest zaznaczona, nowe wiersze karty czasu pracy zostaną utworzone przy użyciu ustawień karty czasu pracy skonfigurowanych jako ulubione.</span><span class="sxs-lookup"><span data-stu-id="a402a-114">If this option is selected, new timesheet lines will be created by using the timesheet settings that were configured as favorites.</span></span>  
4. <span data-ttu-id="a402a-115">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a402a-115">Click **OK**.</span></span>
5. <span data-ttu-id="a402a-116">Kliknij opcję **Nowy wiersz**.</span><span class="sxs-lookup"><span data-stu-id="a402a-116">Click **New line**.</span></span>
6. <span data-ttu-id="a402a-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="a402a-117">In the list, mark the selected row.</span></span> <span data-ttu-id="a402a-118">W polu **Firma** jest domyślnie wyświetlana bieżąca firma.</span><span class="sxs-lookup"><span data-stu-id="a402a-118">The **Legal Entity** field displays the current Legal entity by default.</span></span>   
7. <span data-ttu-id="a402a-119">W polu **Projekt** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a402a-119">In the **Project** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a402a-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a402a-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="a402a-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a402a-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="a402a-122">W polu **Numer działania** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a402a-122">In the **Activity number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="a402a-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a402a-123">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a402a-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a402a-124">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="a402a-125">W polu **Kategoria** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="a402a-125">In the **Category** field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="a402a-126">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a402a-126">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="a402a-127">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a402a-127">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="a402a-128">Wprowadź liczbę godzin przepracowanych każdego dnia.</span><span class="sxs-lookup"><span data-stu-id="a402a-128">Enter the number of hours worked each day.</span></span> <span data-ttu-id="a402a-129">Wprowadź godziny w formacie dziesiętnym.</span><span class="sxs-lookup"><span data-stu-id="a402a-129">Enter the hours in decimal format.</span></span> <span data-ttu-id="a402a-130">Na przykład, jeśli użytkownik pracował przez dwie godziny i piętnaście minut, wprowadź 2.25.</span><span class="sxs-lookup"><span data-stu-id="a402a-130">For example, if you worked for two hours and fifteen minutes, enter 2.25.</span></span>   
17. <span data-ttu-id="a402a-131">W polu **Szczegóły wiersza** są dostępne następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="a402a-131">In **Line details**, the following options are available:</span></span>
    - <span data-ttu-id="a402a-132">Dodaj informacje o podatkach i wymiarach finansowych na kartach **Ogólne** i **Wymiary finansowe**.</span><span class="sxs-lookup"><span data-stu-id="a402a-132">Add information about taxes and financial dimensions in the **General** and the **Financial Dimensions** tab.</span></span>
    - <span data-ttu-id="a402a-133">Dodaj komentarze dotyczące wiersza karty czasu pracy na karcie **Komentarz**.</span><span class="sxs-lookup"><span data-stu-id="a402a-133">Add comments about the timesheet line in the **Comment** tab.</span></span>
20. <span data-ttu-id="a402a-134">W **okienku akcji** kliknij **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="a402a-134">In the **Action pane**, click **Workflow** to open the drop dialog.</span></span>
21. <span data-ttu-id="a402a-135">Kliknij przycisk **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="a402a-135">Click **Submit**.</span></span>
22. <span data-ttu-id="a402a-136">Kliknij przycisk **Prześlij**.</span><span class="sxs-lookup"><span data-stu-id="a402a-136">Click **Submit**.</span></span>

