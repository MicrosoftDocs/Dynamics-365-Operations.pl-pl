---
title: "Dystrybucja i wypełnianie kwestionariusza"
description: "W tym temacie opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać."
author: kherr75
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 3954ec2a06c7a2ec964b656e088f8c677094c963
ms.contentlocale: pl-pl
ms.lasthandoff: 02/07/2018

---

# <a name="distribute-and-complete-a-questionnaire"></a><span data-ttu-id="4beaa-103">Dystrybucja i wypełnianie kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="4beaa-103">Distribute and complete a questionnaire</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="4beaa-104">W tym temacie opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać.</span><span class="sxs-lookup"><span data-stu-id="4beaa-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="4beaa-105">Istnieje wiele sposobów dystrybucji kwestionariusza:</span><span class="sxs-lookup"><span data-stu-id="4beaa-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="4beaa-106">Oznacz kwestionariusz jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="4beaa-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="4beaa-107">Kwestionariusz będzie dostępny dla wszystkich pracowników, chyba że ustawiono grupę kwestionariusza, która nie ma do niego dostępu.</span><span class="sxs-lookup"><span data-stu-id="4beaa-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="4beaa-108">Przypisz prawa grupie kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="4beaa-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="4beaa-109">Kwestionariusz będzie dostępny dla wszystkich członków wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="4beaa-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="4beaa-110">Utwórz zaplanowane sesje odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4beaa-110">Create planned answer sessions.</span></span> <span data-ttu-id="4beaa-111">Kwestionariusz będzie dostępny wyłącznie dla konkretnej osoby.</span><span class="sxs-lookup"><span data-stu-id="4beaa-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="4beaa-112">Utwórz harmonogram.</span><span class="sxs-lookup"><span data-stu-id="4beaa-112">Create a schedule.</span></span> <span data-ttu-id="4beaa-113">Kwestionariusz można być dostępny dla wielu osób.</span><span class="sxs-lookup"><span data-stu-id="4beaa-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="4beaa-114">Oznaczanie kwestionariusza jako aktywnego</span><span class="sxs-lookup"><span data-stu-id="4beaa-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="4beaa-115">Ustawiając pole **Aktywne** jako **Tak** na stronie **Kwestionariusze**, można udostępnić kwestionariusz wszystkim pracownikom do wypełnienia.</span><span class="sxs-lookup"><span data-stu-id="4beaa-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="4beaa-116">Respondenci mogą wypełnić kwestionariusz wiele razy.</span><span class="sxs-lookup"><span data-stu-id="4beaa-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="4beaa-117">Ta funkcja jest przydatna do cyklicznego zbierania opinii przez cały rok.</span><span class="sxs-lookup"><span data-stu-id="4beaa-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="4beaa-118">Na przykład można przygotować kwestionariusz dla pracowników, aby wyrazili opinię na temat jakości posiłków w stołówce zakładowej.</span><span class="sxs-lookup"><span data-stu-id="4beaa-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="4beaa-119">Grupy kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="4beaa-119">Questionnaire groups</span></span>
<span data-ttu-id="4beaa-120">Można ustawić grupy kwestionariusza i uwzględnić respondentów, do których należy przesłać kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="4beaa-121">Grupy kwestionariusza można utworzyć na następujących stronach:</span><span class="sxs-lookup"><span data-stu-id="4beaa-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="4beaa-122">**Grupy kwestionariuszy**— tylko osoby w grupie kwestionariusza mogą wypełnić wybrany kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="4beaa-123">Na przykład grupą docelową są kontrahenci, więc możesz utworzyć grupę kwestionariusza dla tych respondentów.</span><span class="sxs-lookup"><span data-stu-id="4beaa-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="4beaa-124">**Członkowie grupy kwestionariuszy** — do grup kwestionariuszy można dodawać osoby.</span><span class="sxs-lookup"><span data-stu-id="4beaa-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="4beaa-125">Aby przypisać grupę kwestionariusza do kwestionariusza, na stronie **Kwestionariusze** kliknij opcję **Prawa użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="4beaa-126">Po zapisaniu kwestionariusza jako aktywny członkowie grupy kwestionariusza mogą wypełnić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="4beaa-127">Ta funkcja jest przydatna do testowania kwestionariusza na wybranej grupie osób przed udostępnieniem go szerszej grupie respondentów lub kiedy chcesz skierować kwestionariusz do bardzo określonej grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="4beaa-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="4beaa-128">Planowane sesje odpowiedzi w kwestionariuszu</span><span class="sxs-lookup"><span data-stu-id="4beaa-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="4beaa-129">Zaplanowane sesje odpowiedzi to kwestionariusze, które zostały opracowane i wybrane dla respondentów.</span><span class="sxs-lookup"><span data-stu-id="4beaa-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> <span data-ttu-id="4beaa-130">**Uwaga:** Przed skonfigurowaniem zaplanowanych sesji odpowiedzi należy zaprojektować kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-130">**Note** Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="4beaa-131">Na stronie **Planowana sesja odpowiedzi** można utworzyć planowaną sesję odpowiedzi dla pojedynczego pracownika.</span><span class="sxs-lookup"><span data-stu-id="4beaa-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="4beaa-132">Lista na tej stronie zawiera wszystkie zaplanowane kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="4beaa-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="4beaa-133">Planowane sesje odpowiedzi są również używane na stronie **Harmonogramy kwestionariuszy**, gdzie można zaplanować kwestionariusze dla grup osób takich jak:</span><span class="sxs-lookup"><span data-stu-id="4beaa-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="4beaa-134">Pracownicy</span><span class="sxs-lookup"><span data-stu-id="4beaa-134">Employees</span></span>
-   <span data-ttu-id="4beaa-135">Uczestnicy kursu</span><span class="sxs-lookup"><span data-stu-id="4beaa-135">Course participants</span></span>
-   <span data-ttu-id="4beaa-136">Jednostki organizacyjne</span><span class="sxs-lookup"><span data-stu-id="4beaa-136">Organizational units</span></span>

<span data-ttu-id="4beaa-137">Każda osoba może wypełnić kwestionariusz tylko raz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="4beaa-138">Planowanie kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="4beaa-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="4beaa-139">Można opcjonalnie zaplanować kwestionariusz dla wielu respondentów.</span><span class="sxs-lookup"><span data-stu-id="4beaa-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="4beaa-140">Typy planowania</span><span class="sxs-lookup"><span data-stu-id="4beaa-140">Planning types</span></span>

<span data-ttu-id="4beaa-141">Typy planowania są wymagane, aby zaplanować zaplanowane sesje odpowiedzi dla wielu respondentów.</span><span class="sxs-lookup"><span data-stu-id="4beaa-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="4beaa-142">Typy planowania są używane do klasyfikowania harmonogramów kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="4beaa-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="4beaa-143">Na przykład można ustalić harmonogram kwestionariuszy do następujących celów:</span><span class="sxs-lookup"><span data-stu-id="4beaa-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="4beaa-144">Ocena</span><span class="sxs-lookup"><span data-stu-id="4beaa-144">Evaluation</span></span>
-   <span data-ttu-id="4beaa-145">Przegląd</span><span class="sxs-lookup"><span data-stu-id="4beaa-145">Survey</span></span>
-   <span data-ttu-id="4beaa-146">Testowanie</span><span class="sxs-lookup"><span data-stu-id="4beaa-146">Testing</span></span>

<span data-ttu-id="4beaa-147">Na stronie **harmonogramów kwestionariuszy** można określić typy planowania dla harmonogramu kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="4beaa-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="4beaa-148">Typy odwołań do kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="4beaa-148">Reference types for questionnaire</span></span>

<span data-ttu-id="4beaa-149">Typy odwołań służą do wprowadzania kryteriów dla respondentów, które można wybrać podczas planowania kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="4beaa-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="4beaa-150">Użyj strony **typy odwołań** do skonfigurowania odwołań do kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="4beaa-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="4beaa-151">Każdy typ odwołania odpowiada tabeli w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4beaa-151">Each reference type corresponds to a table in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="4beaa-152">Podczas tworzenia harmonogramów kwestionariuszy można określić poszczególne rekordy w tabeli lub zakres rekordów, które będzie można skojarzyć z kwestionariuszem.</span><span class="sxs-lookup"><span data-stu-id="4beaa-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="4beaa-153">Na przykład zaznaczenie w tabeli kursów pozwala określić, do których kursów będzie się odnosić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="4beaa-154">Po skonfigurowaniu odwołanie do tabeli kursów, niektóre pola i przyciski na stronie **kursów** stają się dostępne.</span><span class="sxs-lookup"><span data-stu-id="4beaa-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="4beaa-155">Harmonogramy kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="4beaa-155">Questionnaire schedules</span></span>

<span data-ttu-id="4beaa-156">Harmonogramy kwestionariuszy służą do generowania wielu planowanych sesji odpowiedzi dla grupy użytkowników, na podstawie typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="4beaa-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="4beaa-157">Utwórz harmonogram na stronie **Harmonogramy kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="4beaa-158">Wybierz typ planowania, aby skategoryzować harmonogram, a także wybierz typ odwołania, które powinno być używane do zapytań o konkretnych użytkowników systemu.</span><span class="sxs-lookup"><span data-stu-id="4beaa-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="4beaa-159">Na przykład jeśli wybierzesz typ odwołania do tabeli kursów, możesz wybrać określony kurs w polu **Odwołanie**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="4beaa-160">Kliknij **Szczegóły ustawień**, aby wybrać kwestionariusz i inne kryteria.</span><span class="sxs-lookup"><span data-stu-id="4beaa-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="4beaa-161">Na przykład można określić imię i nazwisko instruktora jako kryterium, jeśli kwestionariusz służy do oceny instruktora.</span><span class="sxs-lookup"><span data-stu-id="4beaa-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="4beaa-162">Po zakończeniu wprowadzania szczegółów konfiguracji system generuje zaplanowane sesje odpowiedzi dla użytkowników, którzy są uwzględnieni w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="4beaa-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="4beaa-163">Kliknij **Zaplanowane sesje odpowiedzi** w celu wyświetlania sesji odpowiedzi dla harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="4beaa-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="4beaa-164">Można ręcznie utworzyć dodatkowe planowane sesje odpowiedzi lub usunąć planowane sesje odpowiedzi, które nie otrzymały odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4beaa-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="4beaa-165">Kliknij kolejno opcje **Funkcje** &gt; **Start**, aby udostępnić kwestionariusz użytkownikom w powiązanych zaplanowanych sesjach odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4beaa-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="4beaa-166">Kliknij **Odpowiedzi** w celu wyświetlania odpowiedzi z wypełnionych kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="4beaa-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="4beaa-167">Opcjonalnie można skopiować ustawienia harmonogramu kwestionariusza, zaplanowanych sesji odpowiedzi i odpowiedzi do nowego harmonogramu kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="4beaa-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="4beaa-168">Powiadamianie respondentów o kwestionariuszach, które są dla nich dostępne</span><span class="sxs-lookup"><span data-stu-id="4beaa-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="4beaa-169">Gdy rozprowadzasz kwestionariusz, musisz powiadomić respondentów, że kwestionariusze są dla nich dostępne.</span><span class="sxs-lookup"><span data-stu-id="4beaa-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="4beaa-170">Powiadamianie respondentów o planowanej sesji odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="4beaa-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="4beaa-171">Jeśli używasz planowanej sesji odpowiedzi, należy powiadomić wybraną osobę bezpośrednio, np. telefoniczne lub e-mailem.</span><span class="sxs-lookup"><span data-stu-id="4beaa-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="4beaa-172">Powiadamianie respondentów o planowaniu</span><span class="sxs-lookup"><span data-stu-id="4beaa-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="4beaa-173">Na stronie **Harmonogramy kwestionariuszy** można przygotować i wysłać wiadomość e-mail do wszystkich respondentów przypisanych do danego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="4beaa-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="4beaa-174">Wprowadź tekst wiadomości e-mail na karcie **Wiadomość e-mail samoobsługi pracownika**. Po rozpoczęciu harmonogramu kliknij opcję **Funkcje** &gt; **Wyślij wiadomość e-mail**, aby wygenerować i wysłać wiadomość e-mail do osób udzielających odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4beaa-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="4beaa-175">Respondenci mogą następnie zalogować się w witrynie i wypełnić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="4beaa-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> <span data-ttu-id="4beaa-176">**Uwaga:** Zanim będzie można skorzystać z funkcji poczty e-mail, administrator IT musi wprowadzić ustawienia poczty e-mail na stronie **Parametry poczty e-mail**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-176">**Note** Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="4beaa-177">Kończenie planowanego arkusza</span><span class="sxs-lookup"><span data-stu-id="4beaa-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="4beaa-178">Można zakończyć zaplanowany kwestionariusz po ukończeniu przez wszystkich respondentów przypisanych do nich sesji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="4beaa-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="4beaa-179">Po zakończeniu zaplanowanego kwestionariusza, nie można skopiować jego ustawień do nowego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="4beaa-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> <span data-ttu-id="4beaa-180">**Uwaga:** Jeśli co najmniej jeden respondent nie wypełnił kwestionariusza, a mimo to planowanie ma zostać zakończone, najpierw usuń odpowiednich respondentów z listy na stronie **Planowana sesja odpowiedzi**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-180">**Note** If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="4beaa-181">Po wykonaniu tej czynności będzie można zakończyć planowanie.</span><span class="sxs-lookup"><span data-stu-id="4beaa-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="4beaa-182">Wypełnianie kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="4beaa-182">Completing questionnaires</span></span>
<span data-ttu-id="4beaa-183">Po zaprojektowaniu i rozesłaniu kwestionariusza, kwestionariusz może zostać wypełniony przez wybranych respondentów.</span><span class="sxs-lookup"><span data-stu-id="4beaa-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="4beaa-184">Kwestionariusze można wypełniać w dwóch lokalizacjach:</span><span class="sxs-lookup"><span data-stu-id="4beaa-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="4beaa-185">W okienku nawigacji kliknij kolejno opcje **Kwestionariusze** &gt; **Dystrybuuj** &gt; **Wypełnianie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="4beaa-186">W obszarze Samoobsługa pracownika etatowego kliknij **Kwestionariusze do wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="4beaa-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="4beaa-187">Kwestionariusze można udostępnić wszystkich osobom w sieci, określonym użytkownikom lub grupom użytkowników.</span><span class="sxs-lookup"><span data-stu-id="4beaa-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="see-also"></a><span data-ttu-id="4beaa-188">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4beaa-188">See also</span></span>
--------

[<span data-ttu-id="4beaa-189">Projektowanie kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="4beaa-189">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="4beaa-190">Używanie kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="4beaa-190">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="4beaa-191">Wyświetlanie i ocena wyników kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="4beaa-191">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)



