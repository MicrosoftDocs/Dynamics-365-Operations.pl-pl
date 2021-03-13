---
title: Zgłaszanie postępu za pomocą urządzenia przenośnego zadania
description: W tej procedurze pokazano sposób uruchamiania i raportowania o postępie zadania produkcyjnego w formularzu rejestracji urządzenia obsługującego zadania.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationTouch, JmgRegistrationTouchUserConfiguration, JmgRegistrationTouchStart, JmgRegistrationTouchReportFeedback, JmgRegistrationTouchAssignedJobs, JmgRegistrationTouchBreak, JmgRegistrationTouchLeave, JmgRegistrationTouchIndirectActivity, JmgDialogForm, JmgRegistrationTouchReportProgress, JmgFeedbackWizard, JmgJobBundleProdFeedback
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c08822dc3960ba5fc85399ca236a31aaf2c38f1f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010954"
---
# <a name="report-progress-on-a-mobile-job-device"></a><span data-ttu-id="f182a-103">Zgłaszanie postępu za pomocą urządzenia przenośnego zadania</span><span class="sxs-lookup"><span data-stu-id="f182a-103">Report progress on a mobile job device</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f182a-104">W tej procedurze pokazano sposób uruchamiania i raportowania o postępie zadania produkcyjnego w formularzu rejestracji urządzenia obsługującego zadania.</span><span class="sxs-lookup"><span data-stu-id="f182a-104">This procedure shows you how to start and report progress on a production job in the job device registration form.</span></span>



<span data-ttu-id="f182a-105">Aby można było uruchomić tę procedurę, musisz mieć rolę Administrator systemu lub Operator maszyny skojarzoną ze swoim kontem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f182a-105">To be able to run this procedure you must have the System administator or Machine Operator role associated with the user account.</span></span>

1. <span data-ttu-id="f182a-106">Wybierz kolejno opcje Kontrola produkcji > Wykonywanie produkcji > Urządzenie karty zadań.</span><span class="sxs-lookup"><span data-stu-id="f182a-106">Go to Production control > Manufacturing execution > Job card device.</span></span>
2. <span data-ttu-id="f182a-107">W polu WorkerTextField wprowadź dane karty identyfikacyjnej pracownika.</span><span class="sxs-lookup"><span data-stu-id="f182a-107">In the WorkerTextField field, enter the badge of a worker.</span></span> <span data-ttu-id="f182a-108">W przypadku danych firmy demonstracyjnej USMF wpisz „123”, co jest identyfikatorem użytkownika Christina Portra.</span><span class="sxs-lookup"><span data-stu-id="f182a-108">In the USMF demo data type '123' for Christina Portra..</span></span>
3. <span data-ttu-id="f182a-109">Kliknij przycisk Zaloguj się.</span><span class="sxs-lookup"><span data-stu-id="f182a-109">Click Log in.</span></span>
4. <span data-ttu-id="f182a-110">Kliknij przycisk Filtr.</span><span class="sxs-lookup"><span data-stu-id="f182a-110">Click the Filter button.</span></span>
5. <span data-ttu-id="f182a-111">Zaznacz pole wyboru Zastosuj filtr konfiguracji lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="f182a-111">Check or uncheck the Apply configuration filter check box.</span></span> <span data-ttu-id="f182a-112">Jeśli ustawisz filtr, można użyć jednostki produkcyjnej 110 z firmy USMF.</span><span class="sxs-lookup"><span data-stu-id="f182a-112">If you set a filter you can use production unit 110 in USMF.</span></span>
6. <span data-ttu-id="f182a-113">W polu Jednostka produkcyjna wybierz grupę zasobów dla zadań produkcyjnych, których może używać pracownik.</span><span class="sxs-lookup"><span data-stu-id="f182a-113">In the Production unit field, select the ressource group for which production jobs the worker can work on.</span></span>
7. <span data-ttu-id="f182a-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="f182a-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f182a-115">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f182a-115">Click OK.</span></span>
9. <span data-ttu-id="f182a-116">Kliknij przycisk Uruchom zadanie.</span><span class="sxs-lookup"><span data-stu-id="f182a-116">Click the Start job button.</span></span>
10. <span data-ttu-id="f182a-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f182a-117">Click OK.</span></span>
11. <span data-ttu-id="f182a-118">Kliknij przycisk Zgłaszanie postępu.</span><span class="sxs-lookup"><span data-stu-id="f182a-118">Click the Report progress button.</span></span>
12. <span data-ttu-id="f182a-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f182a-119">Click OK.</span></span>
13. <span data-ttu-id="f182a-120">Kliknij przycisk Następne zadanie.</span><span class="sxs-lookup"><span data-stu-id="f182a-120">Click the Next job button.</span></span>
14. <span data-ttu-id="f182a-121">Kliknij przycisk Przypisane, aby zobaczyć przegląd wszystkich zadań produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="f182a-121">Click the Assigned to see an overview of all production jobs button.</span></span>
15. <span data-ttu-id="f182a-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="f182a-122">Close the page.</span></span>
16. <span data-ttu-id="f182a-123">Kliknij przycisk Przerwa.</span><span class="sxs-lookup"><span data-stu-id="f182a-123">Click the Break button.</span></span>
17. <span data-ttu-id="f182a-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="f182a-124">In the list, find and select the desired record.</span></span>
18. <span data-ttu-id="f182a-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f182a-125">Click OK.</span></span>
19. <span data-ttu-id="f182a-126">Kliknij przycisk Opuszczanie.</span><span class="sxs-lookup"><span data-stu-id="f182a-126">Click the Leaving button.</span></span>
20. <span data-ttu-id="f182a-127">Kliknij przycisk wylogowywania.</span><span class="sxs-lookup"><span data-stu-id="f182a-127">Select to log out.</span></span>
21. <span data-ttu-id="f182a-128">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f182a-128">Click OK.</span></span>
22. <span data-ttu-id="f182a-129">W polu WorkerTextField zaloguj się ponownie.</span><span class="sxs-lookup"><span data-stu-id="f182a-129">In the WorkerTextField field, log in again.</span></span> <span data-ttu-id="f182a-130">Można wybrać pracownika „123” z danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="f182a-130">You can select worker '123' in USMF demo data.</span></span>
23. <span data-ttu-id="f182a-131">Kliknij przycisk Zaloguj się.</span><span class="sxs-lookup"><span data-stu-id="f182a-131">Click Log in.</span></span>
24. <span data-ttu-id="f182a-132">Kliknij przycisk Zatrzymaj przerwę.</span><span class="sxs-lookup"><span data-stu-id="f182a-132">Click Stop break.</span></span>
25. <span data-ttu-id="f182a-133">Kliknij przycisk Działanie.</span><span class="sxs-lookup"><span data-stu-id="f182a-133">Click the Activity button.</span></span>
26. <span data-ttu-id="f182a-134">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="f182a-134">Click Cancel.</span></span>
27. <span data-ttu-id="f182a-135">Kliknij przycisk Opuszczanie.</span><span class="sxs-lookup"><span data-stu-id="f182a-135">Click the Leaving button.</span></span>
28. <span data-ttu-id="f182a-136">Kliknij przycisk wyrejestrowania.</span><span class="sxs-lookup"><span data-stu-id="f182a-136">Select to clock out.</span></span>
29. <span data-ttu-id="f182a-137">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="f182a-137">Click OK.</span></span>
30. <span data-ttu-id="f182a-138">Wybierz przyczynę, dlaczego wyrejestrowujesz się wcześniej.</span><span class="sxs-lookup"><span data-stu-id="f182a-138">Select a reason why you are clocking out early.</span></span>

