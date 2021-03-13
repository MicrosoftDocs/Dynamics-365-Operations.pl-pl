---
title: Analizowanie wyników kwestionariusza
description: Statystyki kwestionariusza mogą służyć do obliczania wartości średnich, sum i wartości procentowych na podstawie zbioru danych demograficznych.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b49868b76dcc0a5df420e56fd1fc2477c475596
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115181"
---
# <a name="analyzing-questionnaire-results"></a><span data-ttu-id="46777-103">Analizowanie wyników kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="46777-103">Analyzing questionnaire results</span></span>



<span data-ttu-id="46777-104">Statystyki kwestionariusza mogą służyć do obliczania wartości średnich, sum i wartości procentowych na podstawie zbioru danych demograficznych.</span><span class="sxs-lookup"><span data-stu-id="46777-104">Questionnaire statistics can be used to calculate averages, totals, and percentages based on a set of demographic data.</span></span> <span data-ttu-id="46777-105">Aby rozpocząć tę procedurę, wybierz kolejno opcje Kwestionariusz > Wyświetl i analizuj wyniki > Statystyki kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="46777-105">To begin this procedure, go to Questionnaire > View and analyze results > Questionnaire statistics.</span></span> <span data-ttu-id="46777-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="46777-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-statistics-record"></a><span data-ttu-id="46777-107">Tworzenie rekordu statystyk kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="46777-107">Create a Questionnaire statistics record</span></span>
1. <span data-ttu-id="46777-108">Przejdź do okna Statystyki kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="46777-108">Go to Questionnaire statistics.</span></span>
2. <span data-ttu-id="46777-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="46777-109">Click New.</span></span>
3. <span data-ttu-id="46777-110">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="46777-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="46777-111">W polu Statystyki wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="46777-111">In the Statistics field, type a value.</span></span>
5. <span data-ttu-id="46777-112">W polu Opis wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="46777-112">In the Description field, type a value.</span></span>
6. <span data-ttu-id="46777-113">W polu Kwestionariusz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="46777-113">In the Questionnaire field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="46777-114">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="46777-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="46777-115">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="46777-115">Click the General tab.</span></span>
    * <span data-ttu-id="46777-116">Wskaż, czy chcesz uwzględniać wyniki anonimowe czy wyniki od pracowników, osób kontaktowych i kandydatów.</span><span class="sxs-lookup"><span data-stu-id="46777-116">Select if you want to include anonymous results or results from workers, contacts, and applicants.</span></span>  
9. <span data-ttu-id="46777-117">Zaznacz lub wyczyść pole wyboru Pracownik.</span><span class="sxs-lookup"><span data-stu-id="46777-117">Select or clear the Worker check box.</span></span>
    * <span data-ttu-id="46777-118">Jeśli będziesz oglądać wyniki według stażu pracy lub wieku, określ interwały, których chcesz używać do grupowania wyników.</span><span class="sxs-lookup"><span data-stu-id="46777-118">If you will be viewing the results by seniority or age, specify the intervals that you would like to use for grouping the results.</span></span>  
    * <span data-ttu-id="46777-119">Wprowadzenie wartości 5 dla okresu wieku spowoduje grupowanie wyników w oparciu o pięcioletnie interwały wieku.</span><span class="sxs-lookup"><span data-stu-id="46777-119">Entering a 5 for the age interval will group the results based on five-year age intervals.</span></span>  
10. <span data-ttu-id="46777-120">W polu Wiek wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="46777-120">In the Age field, enter a number.</span></span>
    * <span data-ttu-id="46777-121">Wskaż, czy chcesz wykonać obliczenie dla całego kwestionariusza, dla każdej grupy wyników, dla każdego pytania czy dla każdego wiersza pytań.</span><span class="sxs-lookup"><span data-stu-id="46777-121">Select if you want to run the calculation against the entire questionnaire, for each result group, for each question, or for each question row.</span></span>  
    * <span data-ttu-id="46777-122">Określ, jak chcesz grupować wyniki.</span><span class="sxs-lookup"><span data-stu-id="46777-122">Select how you would like to group the results.</span></span>  
    * <span data-ttu-id="46777-123">Na przykład przy obliczaniu średniej liczby punktów na pytanie warto oglądać pytania pogrupowane według grup wyników.</span><span class="sxs-lookup"><span data-stu-id="46777-123">For example, if you calculate the average points per question, you may want to see the questions grouped by Result group.</span></span>  
    * <span data-ttu-id="46777-124">Zaznacz dane, które będą podstawą obliczeń.</span><span class="sxs-lookup"><span data-stu-id="46777-124">Select the data to base the calculation on.</span></span>  
    * <span data-ttu-id="46777-125">Na przykład jeśli chcesz zobaczyć średni procent uzyskiwany w kwestionariuszu przez pracowników w porównaniu ze średnią liczba punktów osiąganą przez pracowników.</span><span class="sxs-lookup"><span data-stu-id="46777-125">For example, if you want to see the average percent received on the questionnaire across your workers versus the average number of points achieved across your workers.</span></span>  
11. <span data-ttu-id="46777-126">Kliknij kartę Zakres.</span><span class="sxs-lookup"><span data-stu-id="46777-126">Click the Range tab.</span></span>
    * <span data-ttu-id="46777-127">Użyj zakresów, aby ograniczyć zestaw wyników tylko do tych spełniających kryteria zakresu.</span><span class="sxs-lookup"><span data-stu-id="46777-127">Use ranges to limit your result set to only those meeting the Range criteria.</span></span>  
12. <span data-ttu-id="46777-128">Kliknij kartę Grupowanie wg.</span><span class="sxs-lookup"><span data-stu-id="46777-128">Click the Grouping by tab.</span></span>
    * <span data-ttu-id="46777-129">Za pomocą grup określ sposób wyświetlania wyników.</span><span class="sxs-lookup"><span data-stu-id="46777-129">Use Groupings to determine how the results should be displayed.</span></span>  
    * <span data-ttu-id="46777-130">Na przykład pogrupuj wyniki najpierw według płci, a następnie według wieku.</span><span class="sxs-lookup"><span data-stu-id="46777-130">For example, group the results first by gender, then by age.</span></span>  
13. <span data-ttu-id="46777-131">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="46777-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="46777-132">Przenieś grupy na stronę Wybrane i umieść je w żądanej kolejności.</span><span class="sxs-lookup"><span data-stu-id="46777-132">Move the groupings into the Selected side and place them in the desired order.</span></span>  

## <a name="execute-the-statistics-calculation"></a><span data-ttu-id="46777-133">Obliczanie statystyk</span><span class="sxs-lookup"><span data-stu-id="46777-133">Execute the statistics calculation</span></span>
1. <span data-ttu-id="46777-134">Kliknij przycisk Wykonaj.</span><span class="sxs-lookup"><span data-stu-id="46777-134">Click Execute.</span></span>
    * <span data-ttu-id="46777-135">Wybierz funkcję obliczania, którą chcesz zastosować do wyników.</span><span class="sxs-lookup"><span data-stu-id="46777-135">Select which calculation function you would like to perform on the results.</span></span>  
    * <span data-ttu-id="46777-136">Na przykład oblicz średnie wartości procentowe z kwestionariusza dla wybranej grupy lub sumy punktów w grupach wyników dla wybranych grup.</span><span class="sxs-lookup"><span data-stu-id="46777-136">For example, calculate the average percentages across the questionnaire for the selected groupings or total the points across the result groups for the selected groupings.</span></span>  
2. <span data-ttu-id="46777-137">Zaznacz lub wyczyść pole wyboru Usuwanie poprzednich wyszukiwań.</span><span class="sxs-lookup"><span data-stu-id="46777-137">Select or clear the Delete previous searches check box.</span></span>
3. <span data-ttu-id="46777-138">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="46777-138">Click OK.</span></span>

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a><span data-ttu-id="46777-139">Służy do wyświetlania wyników sesji statystyk kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="46777-139">View the results of the questionnaire statistics run.</span></span>
1. <span data-ttu-id="46777-140">Kliknij przycisk Wynik.</span><span class="sxs-lookup"><span data-stu-id="46777-140">Click Result.</span></span>
2. <span data-ttu-id="46777-141">Kliknij przycisk Wynik.</span><span class="sxs-lookup"><span data-stu-id="46777-141">Click Result.</span></span>
3. <span data-ttu-id="46777-142">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="46777-142">Close the page.</span></span>

