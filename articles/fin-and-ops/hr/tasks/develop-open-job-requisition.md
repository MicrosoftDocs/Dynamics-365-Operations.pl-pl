--- 
title: Opracowywanie i otwieranie zapotrzebowania na stanowisko
description: "Projekty rekrutacji ułatwiają zarządzanie procesem rekrutacji."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e2d0dcb2e64fa7b901cdc5e4a0469e5f6a76be58
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2018

---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="c3588-103">Opracowywanie i otwieranie zapotrzebowania na stanowisko</span><span class="sxs-lookup"><span data-stu-id="c3588-103">Develop and open job requisition</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c3588-104">Projekty rekrutacji ułatwiają zarządzanie procesem rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="c3588-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="c3588-105">Dla każdego projektu rekrutacji można skonfigurować informacje takie jak zadanie, do którego odbywa się rekrutacja, imię i nazwisko osoby rekrutującej, stan projektu oraz dział, w którym będzie zlokalizowane zadanie.</span><span class="sxs-lookup"><span data-stu-id="c3588-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="c3588-106">Po utworzeniu projektu rekrutacji można napisać ogłoszenie o pracę dla projektu, opublikować oferty na stronach w portalu samoobsługi pracowniczej, skojarzyć podania o pracę z projektem oraz śledzić działania w tym projekcie.</span><span class="sxs-lookup"><span data-stu-id="c3588-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="c3588-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="c3588-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c3588-108">Aby rozpocząć procedurę, wybierz kolejno opcje Zasoby ludzkie > Rekrutacja > Projekty rekrutacji > Projekty rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="c3588-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="c3588-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c3588-109">Click New.</span></span>
2. <span data-ttu-id="c3588-110">W polu Projekt rekrutacji wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c3588-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="c3588-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="c3588-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="c3588-112">W polu Osoba rekrutująca kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c3588-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="c3588-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c3588-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="c3588-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c3588-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="c3588-115">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="c3588-115">Click Select.</span></span>
8. <span data-ttu-id="c3588-116">W polu Dział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c3588-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="c3588-117">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c3588-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="c3588-118">W polu Zadanie kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c3588-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="c3588-119">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c3588-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="c3588-120">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c3588-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="c3588-121">W polu Liczba wolnych posad wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="c3588-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="c3588-122">W polu Menedżer ds. zatrudniania kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c3588-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="c3588-123">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="c3588-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="c3588-124">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c3588-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="c3588-125">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="c3588-125">Click Select.</span></span>
18. <span data-ttu-id="c3588-126">W polu Ostateczny termin zgłoszenia wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c3588-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="c3588-127">Kliknij opcję Nośnik.</span><span class="sxs-lookup"><span data-stu-id="c3588-127">Click Media.</span></span>
    * <span data-ttu-id="c3588-128">Projekty rekrutacji zawierają opcję określenia środków masowego przekazu, które mają być wykorzystywane do reklamowania wolnych stanowisk.</span><span class="sxs-lookup"><span data-stu-id="c3588-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="c3588-129">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="c3588-129">Click New.</span></span>
21. <span data-ttu-id="c3588-130">W polu Nośnik kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="c3588-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="c3588-131">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="c3588-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="c3588-132">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c3588-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="c3588-133">W polu Data końcowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c3588-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="c3588-134">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c3588-134">Click Save.</span></span>
26. <span data-ttu-id="c3588-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c3588-135">Close the page.</span></span>
27. <span data-ttu-id="c3588-136">Kliknij opcję Oferty pracy.</span><span class="sxs-lookup"><span data-stu-id="c3588-136">Click Job ads.</span></span>
28. <span data-ttu-id="c3588-137">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="c3588-137">Click Save.</span></span>
29. <span data-ttu-id="c3588-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="c3588-138">Close the page.</span></span>
30. <span data-ttu-id="c3588-139">Zaznacz lub wyczyść pole wyboru Wyświetl na ekranie samoobsługi pracownika.</span><span class="sxs-lookup"><span data-stu-id="c3588-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="c3588-140">Zaznacz pole wyboru Wyświetl na ekranie samoobsługi pracownika, aby pracownicy widzieli projekt rekrutacji na swoich stronach w portalu samoobsługi pracowniczej.</span><span class="sxs-lookup"><span data-stu-id="c3588-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="c3588-141">Kliknij opcję Stan projektu rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="c3588-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="c3588-142">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="c3588-142">Click Start.</span></span>
    * <span data-ttu-id="c3588-143">Stan Rozpoczęty oznacza, że projekt jest gotowy do przyjmowania wniosków.</span><span class="sxs-lookup"><span data-stu-id="c3588-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="c3588-144">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="c3588-144">Click OK.</span></span>


