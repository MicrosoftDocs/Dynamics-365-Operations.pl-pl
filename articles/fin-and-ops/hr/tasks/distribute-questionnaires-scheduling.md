--- 
title: Dystrybucja kwestionariuszy z wykorzystaniem harmonogramu
description: "Planowanie kwestionariuszy umożliwia planowanie i dystrybucję kwestionariuszy do wielu respondentów."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
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
ms.openlocfilehash: 6795c5ed48ef1d716ddec5cca1a2f6414bb318ce
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="3c555-103">Dystrybucja kwestionariuszy z wykorzystaniem harmonogramu</span><span class="sxs-lookup"><span data-stu-id="3c555-103">Distribute questionnaires using scheduling</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3c555-104">Planowanie kwestionariuszy umożliwia planowanie i dystrybucję kwestionariuszy do wielu respondentów.</span><span class="sxs-lookup"><span data-stu-id="3c555-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="3c555-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="3c555-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="3c555-106">Tworzenie harmonogramu kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="3c555-106">Create a questionnaire schedule</span></span>
1. <span data-ttu-id="3c555-107">Wybierz kolejno opcje Kwestionariusz > Rozdzielenie > Harmonogramy kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="3c555-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>
2. <span data-ttu-id="3c555-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="3c555-108">Click New.</span></span>
3. <span data-ttu-id="3c555-109">W polu Planowanie wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c555-109">In the Scheduling field, type a value.</span></span>
4. <span data-ttu-id="3c555-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="3c555-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3c555-111">Ustaw harmonogram na Anonimowy, jeśli odpowiedzi powinny zostać zarejestrowane bez imion i nazwisk skojarzonych z odpowiedzią.</span><span class="sxs-lookup"><span data-stu-id="3c555-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="3c555-112">Najpierw w parametrach kadr należy skonfigurować zezwalanie na anonimowe wyniki.</span><span class="sxs-lookup"><span data-stu-id="3c555-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  
5. <span data-ttu-id="3c555-113">W polu Typ wybierz typ planowania.</span><span class="sxs-lookup"><span data-stu-id="3c555-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="3c555-114">W tym przykładzie użyjemy typu Zadowolenie.</span><span class="sxs-lookup"><span data-stu-id="3c555-114">In this example we will use the Satisfaction type.</span></span>
6. <span data-ttu-id="3c555-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="3c555-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="3c555-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="3c555-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="3c555-117">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="3c555-117">In the Date field, enter a date.</span></span>
9. <span data-ttu-id="3c555-118">Rozwiń sekcję Wiadomość e-mail samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="3c555-118">Expand the Email for employee self service section.</span></span>
10. <span data-ttu-id="3c555-119">W polu Temat wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c555-119">In the Subject field, type a value.</span></span>
    * <span data-ttu-id="3c555-120">Przykład: Kwestionariusz dostępny</span><span class="sxs-lookup"><span data-stu-id="3c555-120">Example: Questionnaire available</span></span>  
11. <span data-ttu-id="3c555-121">W polu Tekst wprowadź treść swojej wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="3c555-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="3c555-122">Uwaga: zmienna może służyć do zastępowania wartości w systemie.</span><span class="sxs-lookup"><span data-stu-id="3c555-122">Note, the variable can be used to substitute values in the system.</span></span>
    * <span data-ttu-id="3c555-123">Przykład:   Szanowny użytkowniku %P%, Zaloguj się w oknie Samoobsługa pracownika etatowego i wypełnij kwestionariusz zdrowotny pracownika.</span><span class="sxs-lookup"><span data-stu-id="3c555-123">Example:   Dear %P%,  Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="3c555-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="3c555-124">Contoso</span></span>  
12. <span data-ttu-id="3c555-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="3c555-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="3c555-126">Używanie przycisku Szczegóły ustawień do wyboru kwestionariuszy, na które trzeba odpowiedzieć, i do wysyłania kwerend w celu wyboru respondentów.</span><span class="sxs-lookup"><span data-stu-id="3c555-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>
1. <span data-ttu-id="3c555-127">Kliknij przycisk Szczegóły ustawień.</span><span class="sxs-lookup"><span data-stu-id="3c555-127">Click Setup details.</span></span>
2. <span data-ttu-id="3c555-128">Na liście wybierz zapytanie, które ma posłużyć do znalezienia respondentów kwestionariusza w systemie.</span><span class="sxs-lookup"><span data-stu-id="3c555-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>
    * <span data-ttu-id="3c555-129">Przykład: Pracownicy</span><span class="sxs-lookup"><span data-stu-id="3c555-129">Example: Workers</span></span>  
3. <span data-ttu-id="3c555-130">Kliknij przycisk Wyświetl lub zmodyfikuj kwerendę, aby wybrać określone osoby lub skorygować kwerendę, by znaleźć osoby pasujące do określonych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="3c555-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>
    * <span data-ttu-id="3c555-131">Pamiętaj, że wszyscy respondenci muszą być również użytkownikami w systemie.</span><span class="sxs-lookup"><span data-stu-id="3c555-131">Note that all respondents must also be users in the system.</span></span>  
4. <span data-ttu-id="3c555-132">Na liście oznacz wiersz Osoba.</span><span class="sxs-lookup"><span data-stu-id="3c555-132">In the list, mark the row for Person</span></span>
5. <span data-ttu-id="3c555-133">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="3c555-133">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="3c555-134">Wybierz osobę Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="3c555-134">Select Julia Funderburk</span></span>  
6. <span data-ttu-id="3c555-135">Na liście zaznacz osobę Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="3c555-135">In the list, select Julia Funderburk</span></span>
7. <span data-ttu-id="3c555-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c555-136">Click OK.</span></span>
8. <span data-ttu-id="3c555-137">Kliknij kartę Kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="3c555-137">Click the Questionnaires tab.</span></span>
9. <span data-ttu-id="3c555-138">W drzewie rozwiń węzeł typu kwestionariusza Ankieta o zadowoleniu.</span><span class="sxs-lookup"><span data-stu-id="3c555-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>
10. <span data-ttu-id="3c555-139">W drzewie zaznacz pozycję „Ocena zdrowia pracowników”.</span><span class="sxs-lookup"><span data-stu-id="3c555-139">In the tree, check 'Workforce Health Assessment'.</span></span>
11. <span data-ttu-id="3c555-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c555-140">Click OK.</span></span>
12. <span data-ttu-id="3c555-141">Kliknij opcję Planowana sesja odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="3c555-141">Click Planned answer session.</span></span>
    * <span data-ttu-id="3c555-142">Zwróć uwagę, że Planowana sesja odpowiedzi została utworzona dla każdego wybranego użytkownika lub użytkownika dla którego wysłano kwerendę.</span><span class="sxs-lookup"><span data-stu-id="3c555-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  
13. <span data-ttu-id="3c555-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c555-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="3c555-144">Uruchamianie harmonogramu kwestionariusza w celu udostępnienia kwestionariusza respondentom do wypełnienia.</span><span class="sxs-lookup"><span data-stu-id="3c555-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>
1. <span data-ttu-id="3c555-145">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="3c555-145">Click Functions.</span></span>
2. <span data-ttu-id="3c555-146">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="3c555-146">Click Start.</span></span>
3. <span data-ttu-id="3c555-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c555-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="3c555-148">Wysyłanie wiadomości e-mail w celu poinformowania respondentów o dostępnym kwestionariuszu.</span><span class="sxs-lookup"><span data-stu-id="3c555-148">Send the email to inform respondents of the available questionnaire.</span></span>
1. <span data-ttu-id="3c555-149">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="3c555-149">Click Functions.</span></span>
2. <span data-ttu-id="3c555-150">Kliknij przycisk Wyślij wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="3c555-150">Click Send email.</span></span>
3. <span data-ttu-id="3c555-151">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="3c555-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="3c555-152">Używanie Planowanej sesji odpowiedzi do sprawdzania, kto musi wypełnić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="3c555-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>
1. <span data-ttu-id="3c555-153">Kliknij opcję Planowana sesja odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="3c555-153">Click Planned answer session.</span></span>
    * <span data-ttu-id="3c555-154">Usuń wszelkie pozostałe zaplanowane sesje odpowiedzi, aby zakończyć zaplanowaną sesję.</span><span class="sxs-lookup"><span data-stu-id="3c555-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  
2. <span data-ttu-id="3c555-155">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="3c555-155">Click Delete.</span></span>
3. <span data-ttu-id="3c555-156">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="3c555-156">Click Yes.</span></span>
4. <span data-ttu-id="3c555-157">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3c555-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="3c555-158">Zakończ harmonogram, gdy wszyscy respondenci wypełnią kwestionariusz i/lub wszystkie pozostałe zaplanowane sesje odpowiedzi zostaną usunięte.</span><span class="sxs-lookup"><span data-stu-id="3c555-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>
1. <span data-ttu-id="3c555-159">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="3c555-159">Click Functions.</span></span>
2. <span data-ttu-id="3c555-160">Kliknij opcję Koniec.</span><span class="sxs-lookup"><span data-stu-id="3c555-160">Click End.</span></span>
3. <span data-ttu-id="3c555-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="3c555-161">Click OK.</span></span>


