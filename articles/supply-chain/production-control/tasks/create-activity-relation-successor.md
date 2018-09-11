--- 
title: "Tworzenie relacji działań — Zdarzenie następujące"
description: "Przepływ działań w przepływie produkcji oszczędnej jest udokumentowany za pomocą relacji między działaniami."
author: cvocph
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 4ca13d2f1c904fb30cc33e4455010584e7fdd150
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="create-activity-relation-successor"></a><span data-ttu-id="7bd0d-103">Tworzenie relacji działań: Zdarzenie następujące</span><span class="sxs-lookup"><span data-stu-id="7bd0d-103">Create activity relation: Successor</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7bd0d-104">Przepływ działań w przepływie produkcji oszczędnej jest udokumentowany za pomocą relacji między działaniami.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="7bd0d-105">W tym nagraniu pokazano, jak utworzyć relację między działaniami.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="7bd0d-106">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="7bd0d-106">Prerequisites:</span></span>

- <span data-ttu-id="7bd0d-107">Przepływ produkcji i wersja robocza.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="7bd0d-108">Dwa działania następujące po sobie w procesie produkcji są utworzone, ale nie powiązane.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="7bd0d-109">Znajdowanie wersji przepływu produkcji</span><span class="sxs-lookup"><span data-stu-id="7bd0d-109">Find the production flow version</span></span> 
1. <span data-ttu-id="7bd0d-110">Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="7bd0d-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7bd0d-112">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7bd0d-113">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="7bd0d-114">Na liście zaznacz wersję roboczą.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="7bd0d-115">Relacje między działaniami można dodawać do wersji roboczej i aktywnych przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="7bd0d-116">Otwieranie przeglądu działań</span><span class="sxs-lookup"><span data-stu-id="7bd0d-116">Open the activity overview</span></span>
1. <span data-ttu-id="7bd0d-117">Kliknij opcję Działania.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-117">Click Activities.</span></span>
    * <span data-ttu-id="7bd0d-118">Należy zwrócić uwagę, że w formularzu są wyświetlane wszystkie działania przepływu produkcji przydzielone do wersji przepływów produkcji, z którymi pracujesz.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="7bd0d-119">Dodawanie zdarzenia następującego</span><span class="sxs-lookup"><span data-stu-id="7bd0d-119">Add a Successor</span></span>
1. <span data-ttu-id="7bd0d-120">Kliknij opcję Dodaj zdarzenie następujące.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-120">Click Add successor.</span></span>
2. <span data-ttu-id="7bd0d-121">W polu Działanie kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="7bd0d-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="7bd0d-123">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7bd0d-124">Zaznacz pole wyboru Ograniczenie.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="7bd0d-125">W polu Wartość ograniczenia wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="7bd0d-126">Czas ograniczenia to czas, jaki należy zaplanować między zaplanowanym zakończeniem działania poprzedzającego (wymagana data i godzina) a zaplanowanym rozpoczęciem działania następującego.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="7bd0d-127">W polu Jednostki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="7bd0d-128">W polu Wskaźnik czasu cyklu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="7bd0d-129">Jeśli oba działania są wykonywane z tym samym taktem, współczynnik czasu cyklu powinien wynosić 1.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="7bd0d-130">Jeśli zdarzenie poprzedzające odbywa się dwa razy szybciej niż działanie następujące, współczynnik powinien wynosić 2.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="7bd0d-131">Współczynniki czasu cyklu są używane do obliczania poszczególnych czasów cyklu dla działań przepływu produkcji.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="7bd0d-132">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-132">Click OK.</span></span>
10. <span data-ttu-id="7bd0d-133">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-133">Close the page.</span></span>
11. <span data-ttu-id="7bd0d-134">Kliknij kartę GridPanel.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="7bd0d-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-135">Close the page.</span></span>
13. <span data-ttu-id="7bd0d-136">Odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="7bd0d-136">Refresh the page.</span></span>


