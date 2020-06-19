---
title: Dystrybucja kwestionariuszy z wykorzystaniem harmonogramu
description: Planowanie kwestionariuszy umożliwia planowanie i dystrybucję kwestionariuszy do wielu respondentów.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d233938fe553dbd7da7fcc5477097fd885665102
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429501"
---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="a0394-103">Dystrybucja kwestionariuszy z wykorzystaniem harmonogramu</span><span class="sxs-lookup"><span data-stu-id="a0394-103">Distribute questionnaires using scheduling</span></span>

<span data-ttu-id="a0394-104">Planowanie kwestionariuszy umożliwia planowanie i dystrybucję kwestionariuszy do wielu respondentów.</span><span class="sxs-lookup"><span data-stu-id="a0394-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="a0394-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="a0394-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="a0394-106">Tworzenie harmonogramu kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="a0394-106">Create a questionnaire schedule</span></span>

1. <span data-ttu-id="a0394-107">Wybierz kolejno opcje Kwestionariusz > Rozdzielenie > Harmonogramy kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="a0394-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>

2. <span data-ttu-id="a0394-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="a0394-108">Click New.</span></span>

3. <span data-ttu-id="a0394-109">W polu Planowanie wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a0394-109">In the Scheduling field, type a value.</span></span>

4. <span data-ttu-id="a0394-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="a0394-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="a0394-111">Ustaw harmonogram na Anonimowy, jeśli odpowiedzi powinny zostać zarejestrowane bez imion i nazwisk skojarzonych z odpowiedzią.</span><span class="sxs-lookup"><span data-stu-id="a0394-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="a0394-112">Najpierw w parametrach kadr należy skonfigurować zezwalanie na anonimowe wyniki.</span><span class="sxs-lookup"><span data-stu-id="a0394-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  

5. <span data-ttu-id="a0394-113">W polu Typ wybierz typ planowania.</span><span class="sxs-lookup"><span data-stu-id="a0394-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="a0394-114">W tym przykładzie użyjemy typu Zadowolenie.</span><span class="sxs-lookup"><span data-stu-id="a0394-114">In this example we will use the Satisfaction type.</span></span>

6. <span data-ttu-id="a0394-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a0394-115">In the list, find and select the desired record.</span></span>

7. <span data-ttu-id="a0394-116">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="a0394-116">In the list, click the link in the selected row.</span></span>

8. <span data-ttu-id="a0394-117">W polu Data wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="a0394-117">In the Date field, enter a date.</span></span>

9. <span data-ttu-id="a0394-118">Rozwiń sekcję Wiadomość e-mail samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="a0394-118">Expand the Email for employee self service section.</span></span>

10. <span data-ttu-id="a0394-119">W polu Temat wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="a0394-119">In the Subject field, type a value.</span></span>

    * <span data-ttu-id="a0394-120">Przykład: Kwestionariusz dostępny</span><span class="sxs-lookup"><span data-stu-id="a0394-120">Example: Questionnaire available</span></span>  

11. <span data-ttu-id="a0394-121">W polu Tekst wprowadź treść swojej wiadomości e-mail.</span><span class="sxs-lookup"><span data-stu-id="a0394-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="a0394-122">Uwaga: zmienna może służyć do zastępowania wartości w systemie.</span><span class="sxs-lookup"><span data-stu-id="a0394-122">Note, the variable can be used to substitue values in the system.</span></span>

    * <span data-ttu-id="a0394-123">Przykład: Szanowny użytkowniku %P%, Zaloguj się w oknie Samoobsługa pracownika etatowego i wypełnij kwestionariusz zdrowotny pracownika.</span><span class="sxs-lookup"><span data-stu-id="a0394-123">Example: Dear %P%, Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="a0394-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="a0394-124">Contoso</span></span>  

12. <span data-ttu-id="a0394-125">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="a0394-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="a0394-126">Używanie przycisku Szczegóły ustawień do wyboru kwestionariuszy, na które trzeba odpowiedzieć, i do wysyłania kwerend w celu wyboru respondentów.</span><span class="sxs-lookup"><span data-stu-id="a0394-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>

1. <span data-ttu-id="a0394-127">Kliknij przycisk Szczegóły ustawień.</span><span class="sxs-lookup"><span data-stu-id="a0394-127">Click Setup details.</span></span>

2. <span data-ttu-id="a0394-128">Na liście wybierz zapytanie, które ma posłużyć do znalezienia respondentów kwestionariusza w systemie.</span><span class="sxs-lookup"><span data-stu-id="a0394-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>

    * <span data-ttu-id="a0394-129">Przykład: Pracownicy</span><span class="sxs-lookup"><span data-stu-id="a0394-129">Example: Workers</span></span>  

3. <span data-ttu-id="a0394-130">Kliknij przycisk Wyświetl lub zmodyfikuj kwerendę, aby wybrać określone osoby lub skorygować kwerendę, by znaleźć osoby pasujące do określonych kryteriów.</span><span class="sxs-lookup"><span data-stu-id="a0394-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>

    * <span data-ttu-id="a0394-131">Pamiętaj, że wszyscy respondenci muszą być również użytkownikami w systemie.</span><span class="sxs-lookup"><span data-stu-id="a0394-131">Note that all respondents must also be users in the system.</span></span>  

4. <span data-ttu-id="a0394-132">Na liście oznacz wiersz Osoba.</span><span class="sxs-lookup"><span data-stu-id="a0394-132">In the list, mark the row for Person</span></span>

5. <span data-ttu-id="a0394-133">W polu Kryteria wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="a0394-133">In the Criteria field, enter or select a value.</span></span>

    * <span data-ttu-id="a0394-134">Wybierz osobę Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="a0394-134">Select Julia Funderburk</span></span>  

6. <span data-ttu-id="a0394-135">Na liście zaznacz osobę Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="a0394-135">In the list, select Julia Funderburk</span></span>

7. <span data-ttu-id="a0394-136">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a0394-136">Click OK.</span></span>

8. <span data-ttu-id="a0394-137">Kliknij kartę Kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="a0394-137">Click the Questionnaires tab.</span></span>

9. <span data-ttu-id="a0394-138">W drzewie rozwiń węzeł typu kwestionariusza Ankieta o zadowoleniu.</span><span class="sxs-lookup"><span data-stu-id="a0394-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>

10. <span data-ttu-id="a0394-139">W drzewie zaznacz pozycję „Ocena zdrowia pracowników”.</span><span class="sxs-lookup"><span data-stu-id="a0394-139">In the tree, check 'Workforce Health Assessment'.</span></span>

11. <span data-ttu-id="a0394-140">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a0394-140">Click OK.</span></span>

12. <span data-ttu-id="a0394-141">Kliknij opcję Planowana sesja odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="a0394-141">Click Planned answer session.</span></span>

    * <span data-ttu-id="a0394-142">Zwróć uwagę, że Planowana sesja odpowiedzi została utworzona dla każdego wybranego użytkownika lub użytkownika dla którego wysłano kwerendę.</span><span class="sxs-lookup"><span data-stu-id="a0394-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  

13. <span data-ttu-id="a0394-143">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a0394-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="a0394-144">Uruchamianie harmonogramu kwestionariusza w celu udostępnienia kwestionariusza respondentom do wypełnienia.</span><span class="sxs-lookup"><span data-stu-id="a0394-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>

1. <span data-ttu-id="a0394-145">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="a0394-145">Click Functions.</span></span>

2. <span data-ttu-id="a0394-146">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="a0394-146">Click Start.</span></span>

3. <span data-ttu-id="a0394-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a0394-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="a0394-148">Wysyłanie wiadomości e-mail w celu poinformowania respondentów o dostępnym kwestionariuszu.</span><span class="sxs-lookup"><span data-stu-id="a0394-148">Send the email to inform respondents of the available questionnaire.</span></span>

1. <span data-ttu-id="a0394-149">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="a0394-149">Click Functions.</span></span>

2. <span data-ttu-id="a0394-150">Kliknij przycisk Wyślij wiadomość e-mail.</span><span class="sxs-lookup"><span data-stu-id="a0394-150">Click Send email.</span></span>

3. <span data-ttu-id="a0394-151">Kliknij przycisk Anuluj.</span><span class="sxs-lookup"><span data-stu-id="a0394-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="a0394-152">Używanie Planowanej sesji odpowiedzi do sprawdzania, kto musi wypełnić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="a0394-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>

1. <span data-ttu-id="a0394-153">Kliknij opcję Planowana sesja odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="a0394-153">Click Planned answer session.</span></span>

    * <span data-ttu-id="a0394-154">Usuń wszelkie pozostałe zaplanowane sesje odpowiedzi, aby zakończyć zaplanowaną sesję.</span><span class="sxs-lookup"><span data-stu-id="a0394-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  

2. <span data-ttu-id="a0394-155">Kliknij przycisk Usuń.</span><span class="sxs-lookup"><span data-stu-id="a0394-155">Click Delete.</span></span>

3. <span data-ttu-id="a0394-156">Kliknij przycisk Tak.</span><span class="sxs-lookup"><span data-stu-id="a0394-156">Click Yes.</span></span>

4. <span data-ttu-id="a0394-157">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="a0394-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="a0394-158">Zakończ harmonogram, gdy wszyscy respondenci wypełnią kwestionariusz i/lub wszystkie pozostałe zaplanowane sesje odpowiedzi zostaną usunięte.</span><span class="sxs-lookup"><span data-stu-id="a0394-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>

1. <span data-ttu-id="a0394-159">Kliknij przycisk Funkcje.</span><span class="sxs-lookup"><span data-stu-id="a0394-159">Click Functions.</span></span>
2. <span data-ttu-id="a0394-160">Kliknij opcję Koniec.</span><span class="sxs-lookup"><span data-stu-id="a0394-160">Click End.</span></span>
3. <span data-ttu-id="a0394-161">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="a0394-161">Click OK.</span></span>

