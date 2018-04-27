--- 
title: "Tworzenie pytania zamkniętego"
description: "Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: fdfac92b80774adb8376d5c2e945d063173188c8
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="74e8f-103">Tworzenie pytania zamkniętego</span><span class="sxs-lookup"><span data-stu-id="74e8f-103">Create a closed ended question</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="74e8f-104">Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru.</span><span class="sxs-lookup"><span data-stu-id="74e8f-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="74e8f-105">Najpierw należy utworzyć grupę odpowiedzi z odpowiedziami, a następnie pytanie, który będzie używało grupy odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="74e8f-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="74e8f-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="74e8f-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="74e8f-107">Tworzenie grupy odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="74e8f-107">Create an answer group</span></span>
1. <span data-ttu-id="74e8f-108">Wybierz kolejno opcje Kwestionariusz > Projekt > Grupy odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="74e8f-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="74e8f-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-109">Click New.</span></span>
3. <span data-ttu-id="74e8f-110">W polu Grupa odpowiedzi wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="74e8f-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="74e8f-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="74e8f-112">Funkcja Losowo spowoduje losowe rozmieszczanie odpowiedzi w różnej kolejności podczas każdorazowego użycia grupy odpowiedzi do pytania.</span><span class="sxs-lookup"><span data-stu-id="74e8f-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="74e8f-113">Kliknij opcję Odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="74e8f-113">Click Answer.</span></span>
6. <span data-ttu-id="74e8f-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-114">Click New.</span></span>
    * <span data-ttu-id="74e8f-115">Numer kolejny określa kolejność, w jakiej odpowiedzi są wyświetlane, chyba że dla grupy odpowiedzi wybrano opcję Losowo.</span><span class="sxs-lookup"><span data-stu-id="74e8f-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="74e8f-116">Można przyznawać punkty za odpowiedzi z przeznaczeniem do wykorzystania przy ocenianiu wyników kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="74e8f-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="74e8f-117">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="74e8f-118">Poprawną odpowiedź można oznaczyć, aby wskazać, że wybrana odpowiedź jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="74e8f-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="74e8f-119">To może służyć do oceniania wyników kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="74e8f-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="74e8f-120">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="74e8f-121">Przejdź do tworzenia opcji wyboru odpowiedzi dla grupy odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="74e8f-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="74e8f-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-122">Click New.</span></span>
10. <span data-ttu-id="74e8f-123">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="74e8f-124">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="74e8f-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-125">Click New.</span></span>
13. <span data-ttu-id="74e8f-126">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="74e8f-127">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="74e8f-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-128">Click New.</span></span>
16. <span data-ttu-id="74e8f-129">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="74e8f-130">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="74e8f-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-131">Click New.</span></span>
19. <span data-ttu-id="74e8f-132">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="74e8f-133">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="74e8f-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-134">Close the page.</span></span>
22. <span data-ttu-id="74e8f-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="74e8f-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="74e8f-136">Tworzenie pytania</span><span class="sxs-lookup"><span data-stu-id="74e8f-136">Create the question</span></span>
1. <span data-ttu-id="74e8f-137">Wybierz kolejno opcje Kwestionariusz > Projekt > Pytania.</span><span class="sxs-lookup"><span data-stu-id="74e8f-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="74e8f-138">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="74e8f-138">Click New.</span></span>
3. <span data-ttu-id="74e8f-139">Pole Typ służy do grupowania powiązanych pytań.</span><span class="sxs-lookup"><span data-stu-id="74e8f-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="74e8f-140">Dla pytań zamkniętych można używać danych wejściowych typu pole wyboru, przycisk alternatywy lub pole kombi.</span><span class="sxs-lookup"><span data-stu-id="74e8f-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="74e8f-141">W polu Typ danych wejściowych wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="74e8f-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="74e8f-142">W polu Grupa odpowiedzi wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="74e8f-143">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="74e8f-143">In the Text field, type a value.</span></span>


