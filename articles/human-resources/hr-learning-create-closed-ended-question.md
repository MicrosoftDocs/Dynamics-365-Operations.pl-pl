---
title: Tworzenie pytania zamkniętego
description: Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55a41ae639970eb3324a5760af7f6dd5fb8f2ad5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010247"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="ba5b8-103">Tworzenie pytania zamkniętego</span><span class="sxs-lookup"><span data-stu-id="ba5b8-103">Create a closed ended question</span></span>



<span data-ttu-id="ba5b8-104">Pytania zamknięte umożliwiają udostępnienie osobie udzielającej odpowiedzi opcji do wyboru.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="ba5b8-105">Najpierw należy utworzyć grupę odpowiedzi z odpowiedziami, a następnie pytanie, który będzie używało grupy odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="ba5b8-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="ba5b8-107">Tworzenie grupy odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="ba5b8-107">Create an answer group</span></span>
1. <span data-ttu-id="ba5b8-108">Wybierz kolejno opcje Kwestionariusz > Projekt > Grupy odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="ba5b8-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-109">Click New.</span></span>
3. <span data-ttu-id="ba5b8-110">W polu Grupa odpowiedzi wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="ba5b8-111">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="ba5b8-112">Funkcja Losowo spowoduje losowe rozmieszczanie odpowiedzi w różnej kolejności podczas każdorazowego użycia grupy odpowiedzi do pytania.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="ba5b8-113">Kliknij opcję Odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-113">Click Answer.</span></span>
6. <span data-ttu-id="ba5b8-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-114">Click New.</span></span>
    * <span data-ttu-id="ba5b8-115">Numer kolejny określa kolejność, w jakiej odpowiedzi są wyświetlane, chyba że dla grupy odpowiedzi wybrano opcję Losowo.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="ba5b8-116">Można przyznawać punkty za odpowiedzi z przeznaczeniem do wykorzystania przy ocenianiu wyników kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="ba5b8-117">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="ba5b8-118">Poprawną odpowiedź można oznaczyć, aby wskazać, że wybrana odpowiedź jest prawidłowa.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="ba5b8-119">To może służyć do oceniania wyników kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="ba5b8-120">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="ba5b8-121">Przejdź do tworzenia opcji wyboru odpowiedzi dla grupy odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="ba5b8-122">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-122">Click New.</span></span>
10. <span data-ttu-id="ba5b8-123">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="ba5b8-124">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="ba5b8-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-125">Click New.</span></span>
13. <span data-ttu-id="ba5b8-126">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="ba5b8-127">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="ba5b8-128">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-128">Click New.</span></span>
16. <span data-ttu-id="ba5b8-129">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="ba5b8-130">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="ba5b8-131">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-131">Click New.</span></span>
19. <span data-ttu-id="ba5b8-132">W polu Punkty wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="ba5b8-133">W polu Odpowiedź wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="ba5b8-134">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-134">Close the page.</span></span>
22. <span data-ttu-id="ba5b8-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="ba5b8-136">Tworzenie pytania</span><span class="sxs-lookup"><span data-stu-id="ba5b8-136">Create the question</span></span>
1. <span data-ttu-id="ba5b8-137">Wybierz kolejno opcje Kwestionariusz > Projekt > Pytania.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="ba5b8-138">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-138">Click New.</span></span>
3. <span data-ttu-id="ba5b8-139">Pole Typ służy do grupowania powiązanych pytań.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="ba5b8-140">Dla pytań zamkniętych można używać danych wejściowych typu pole wyboru, przycisk alternatywy lub pole kombi.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="ba5b8-141">W polu Typ danych wejściowych wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="ba5b8-142">W polu Grupa odpowiedzi wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="ba5b8-143">W polu Tekst wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ba5b8-143">In the Text field, type a value.</span></span>

