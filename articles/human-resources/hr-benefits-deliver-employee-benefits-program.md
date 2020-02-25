---
title: Dostarczanie programu świadczeń dla pracowników
description: Ten artykuł pokazuje sposób tworzenia elementów świadczenia, które będą używane podczas tworzenia nowego świadczenia.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitElementSetup, HcmBenefit, HcmBenefitNewBenefit, HcmBenefitPlanLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: b8631e4f8cb2947ec7e09de86a7ceb075a83a453
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010270"
---
# <a name="deliver-employee-benefits-program"></a><span data-ttu-id="7fd72-103">Dostarczanie programu świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="7fd72-103">Deliver employee benefits program</span></span>

<span data-ttu-id="7fd72-104">Ten artykuł pokazuje sposób tworzenia elementów świadczenia, które będą używane podczas tworzenia nowego świadczenia.</span><span class="sxs-lookup"><span data-stu-id="7fd72-104">This article shows you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="7fd72-105">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7fd72-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="7fd72-106">Zadanie jest przeznaczona dla menedżer ds. wynagrodzeń i świadczeń.</span><span class="sxs-lookup"><span data-stu-id="7fd72-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="7fd72-107">Tworzenie elementów świadczenia</span><span class="sxs-lookup"><span data-stu-id="7fd72-107">Create benefit elements</span></span>
1. <span data-ttu-id="7fd72-108">To zadanie rozpoczyna się od strony Lista świadczeń.</span><span class="sxs-lookup"><span data-stu-id="7fd72-108">This task starts from the Benefits list page.</span></span> <span data-ttu-id="7fd72-109">Uruchom zadanie, otwierając tę stronę lub przeszukując stronę Lista świadczeń.</span><span class="sxs-lookup"><span data-stu-id="7fd72-109">Start the task by opening that page or searching the Benefits list page.</span></span>
2. <span data-ttu-id="7fd72-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fd72-110">Click New.</span></span>
3. <span data-ttu-id="7fd72-111">W polu Typ nadaj nazwę typowi świadczenia, które tworzysz.</span><span class="sxs-lookup"><span data-stu-id="7fd72-111">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="7fd72-112">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="7fd72-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="7fd72-113">W polu Rejestrowanie współbieżne wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7fd72-113">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="7fd72-114">Aby ograniczyć pracownikom możliwość rejestracji w wielu planach medycznych, zaznacz opcję Jedna rejestracja na typ.</span><span class="sxs-lookup"><span data-stu-id="7fd72-114">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="7fd72-115">W polu Kategoria listy płac wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7fd72-115">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="7fd72-116">Kliknij kartę Plany.</span><span class="sxs-lookup"><span data-stu-id="7fd72-116">Click the Plans tab.</span></span>
8. <span data-ttu-id="7fd72-117">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fd72-117">Click New.</span></span>
9. <span data-ttu-id="7fd72-118">W polu Plan wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fd72-118">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="7fd72-119">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="7fd72-119">In the Description field, type a value.</span></span>
11. <span data-ttu-id="7fd72-120">W polu Typ kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7fd72-120">In the Type field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="7fd72-121">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7fd72-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="7fd72-122">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7fd72-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="7fd72-123">W polu Wpływ na listę płac wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7fd72-123">In the Payroll impact field, select an option.</span></span>
15. <span data-ttu-id="7fd72-124">Kliknij kartę Opcje.</span><span class="sxs-lookup"><span data-stu-id="7fd72-124">Click the Options tab.</span></span>
16. <span data-ttu-id="7fd72-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="7fd72-125">Click New.</span></span>
17. <span data-ttu-id="7fd72-126">W polu Opcja wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="7fd72-126">In the Option field, type a value.</span></span>
18. <span data-ttu-id="7fd72-127">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="7fd72-127">In the Description field, type a value.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="7fd72-128">Tworzenie świadczenia</span><span class="sxs-lookup"><span data-stu-id="7fd72-128">Create a benefit</span></span>
1. <span data-ttu-id="7fd72-129">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="7fd72-129">Close the page.</span></span>
2. <span data-ttu-id="7fd72-130">Wybierz kolejno opcje Zasoby ludzkie > Świadczenia > Świadczenia.</span><span class="sxs-lookup"><span data-stu-id="7fd72-130">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="7fd72-131">Kliknij przycisk Nowy, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="7fd72-131">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="7fd72-132">W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7fd72-132">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7fd72-133">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7fd72-133">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="7fd72-134">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7fd72-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="7fd72-135">W polu Opcja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7fd72-135">In the Option field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="7fd72-136">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7fd72-136">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="7fd72-137">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7fd72-137">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="7fd72-138">W polu Data wprowadzenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="7fd72-138">In the Effective field, enter a date and time.</span></span>
11. <span data-ttu-id="7fd72-139">Kliknij przycisk Utwórz świadczenie.</span><span class="sxs-lookup"><span data-stu-id="7fd72-139">Click Create benefit.</span></span>
12. <span data-ttu-id="7fd72-140">Przełącz rozwinięcie sekcji Szczegóły listy płac.</span><span class="sxs-lookup"><span data-stu-id="7fd72-140">Toggle the expansion of the Payroll details section.</span></span>
13. <span data-ttu-id="7fd72-141">W polu Częstotliwość kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="7fd72-141">In the Frequency field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="7fd72-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="7fd72-142">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="7fd72-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="7fd72-143">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="7fd72-144">W polu Podstawa wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7fd72-144">In the Basis field, select an option.</span></span>
17. <span data-ttu-id="7fd72-145">W polu Kwota lub stawka wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="7fd72-145">In the Amount or rate field, enter a number.</span></span>

