---
title: Dystrybuowanie i planowanie kwestionariuszy
description: W tym artykule opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0329b80615eed6efcc22bb0b140970988f5c306a
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429527"
---
# <a name="distribute-and-schedule-questionnaires"></a><span data-ttu-id="9cb90-103">Dystrybuowanie i planowanie kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="9cb90-103">Distribute and schedule questionnaires</span></span>

<span data-ttu-id="9cb90-104">W tym artykule opisano sposób dystrybuowania kwestionariuszy, które można zaprojektować tak, aby były dostępne dla osoby lub grupy osób, które będą je wypełniać.</span><span class="sxs-lookup"><span data-stu-id="9cb90-104">This article explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="9cb90-105">Istnieje wiele sposobów dystrybucji kwestionariusza:</span><span class="sxs-lookup"><span data-stu-id="9cb90-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="9cb90-106">Oznacz kwestionariusz jako aktywny.</span><span class="sxs-lookup"><span data-stu-id="9cb90-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="9cb90-107">Kwestionariusz będzie dostępny dla wszystkich pracowników, chyba że ustawiono grupę kwestionariusza, która nie ma do niego dostępu.</span><span class="sxs-lookup"><span data-stu-id="9cb90-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="9cb90-108">Przypisz prawa grupie kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="9cb90-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="9cb90-109">Kwestionariusz będzie dostępny dla wszystkich członków wybranej grupy.</span><span class="sxs-lookup"><span data-stu-id="9cb90-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="9cb90-110">Utwórz zaplanowane sesje odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9cb90-110">Create planned answer sessions.</span></span> <span data-ttu-id="9cb90-111">Kwestionariusz będzie dostępny wyłącznie dla konkretnej osoby.</span><span class="sxs-lookup"><span data-stu-id="9cb90-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="9cb90-112">Utwórz harmonogram.</span><span class="sxs-lookup"><span data-stu-id="9cb90-112">Create a schedule.</span></span> <span data-ttu-id="9cb90-113">Kwestionariusz można być dostępny dla wielu osób.</span><span class="sxs-lookup"><span data-stu-id="9cb90-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="9cb90-114">Oznaczanie kwestionariusza jako aktywnego</span><span class="sxs-lookup"><span data-stu-id="9cb90-114">Marking a questionnaire as active</span></span>

<span data-ttu-id="9cb90-115">Ustawiając pole **Aktywne** jako **Tak** na stronie **Kwestionariusze**, można udostępnić kwestionariusz wszystkim pracownikom do wypełnienia.</span><span class="sxs-lookup"><span data-stu-id="9cb90-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="9cb90-116">Respondenci mogą wypełnić kwestionariusz wiele razy.</span><span class="sxs-lookup"><span data-stu-id="9cb90-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="9cb90-117">Ta funkcja jest przydatna do cyklicznego zbierania opinii przez cały rok.</span><span class="sxs-lookup"><span data-stu-id="9cb90-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="9cb90-118">Na przykład można przygotować kwestionariusz dla pracowników, aby wyrazili opinię na temat jakości posiłków w stołówce zakładowej.</span><span class="sxs-lookup"><span data-stu-id="9cb90-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="9cb90-119">Grupy kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="9cb90-119">Questionnaire groups</span></span>

<span data-ttu-id="9cb90-120">Można ustawić grupy kwestionariusza i uwzględnić respondentów, do których należy przesłać kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="9cb90-121">Grupy kwestionariusza można utworzyć na następujących stronach:</span><span class="sxs-lookup"><span data-stu-id="9cb90-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="9cb90-122">**Grupy kwestionariuszy**— tylko osoby w grupie kwestionariusza mogą wypełnić wybrany kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="9cb90-123">Na przykład grupą docelową są kontrahenci, więc możesz utworzyć grupę kwestionariusza dla tych respondentów.</span><span class="sxs-lookup"><span data-stu-id="9cb90-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="9cb90-124">**Członkowie grupy kwestionariuszy** — do grup kwestionariuszy można dodawać osoby.</span><span class="sxs-lookup"><span data-stu-id="9cb90-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="9cb90-125">Aby przypisać grupę kwestionariusza do kwestionariusza, na stronie **Kwestionariusze** kliknij opcję **Prawa użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="9cb90-126">Po zapisaniu kwestionariusza jako aktywny członkowie grupy kwestionariusza mogą wypełnić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="9cb90-127">Ta funkcja jest przydatna do testowania kwestionariusza na wybranej grupie osób przed udostępnieniem go szerszej grupie respondentów lub kiedy chcesz skierować kwestionariusz do bardzo określonej grupy odbiorców.</span><span class="sxs-lookup"><span data-stu-id="9cb90-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="9cb90-128">Planowane sesje odpowiedzi w kwestionariuszu</span><span class="sxs-lookup"><span data-stu-id="9cb90-128">Planned answer sessions in a questionnaire</span></span>

<span data-ttu-id="9cb90-129">Zaplanowane sesje odpowiedzi to kwestionariusze, które zostały opracowane i wybrane dla respondentów.</span><span class="sxs-lookup"><span data-stu-id="9cb90-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> [!NOTE]
> <span data-ttu-id="9cb90-130">Przed skonfigurowaniem zaplanowanych sesji odpowiedzi należy zaprojektować kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-130">Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="9cb90-131">Na stronie **Planowana sesja odpowiedzi** można utworzyć planowaną sesję odpowiedzi dla pojedynczego pracownika.</span><span class="sxs-lookup"><span data-stu-id="9cb90-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="9cb90-132">Lista na tej stronie zawiera wszystkie zaplanowane kwestionariusze.</span><span class="sxs-lookup"><span data-stu-id="9cb90-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="9cb90-133">Planowane sesje odpowiedzi są również używane na stronie **Harmonogramy kwestionariuszy**, gdzie można zaplanować kwestionariusze dla grup osób takich jak:</span><span class="sxs-lookup"><span data-stu-id="9cb90-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="9cb90-134">Pracownicy</span><span class="sxs-lookup"><span data-stu-id="9cb90-134">Employees</span></span>
-   <span data-ttu-id="9cb90-135">Uczestnicy kursu</span><span class="sxs-lookup"><span data-stu-id="9cb90-135">Course participants</span></span>
-   <span data-ttu-id="9cb90-136">Jednostki organizacyjne</span><span class="sxs-lookup"><span data-stu-id="9cb90-136">Organizational units</span></span>

<span data-ttu-id="9cb90-137">Każda osoba może wypełnić kwestionariusz tylko raz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="9cb90-138">Planowanie kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="9cb90-138">Scheduling a questionnaire</span></span>

<span data-ttu-id="9cb90-139">Można opcjonalnie zaplanować kwestionariusz dla wielu respondentów.</span><span class="sxs-lookup"><span data-stu-id="9cb90-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="9cb90-140">Typy planowania</span><span class="sxs-lookup"><span data-stu-id="9cb90-140">Planning types</span></span>

<span data-ttu-id="9cb90-141">Typy planowania są wymagane, aby zaplanować zaplanowane sesje odpowiedzi dla wielu respondentów.</span><span class="sxs-lookup"><span data-stu-id="9cb90-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="9cb90-142">Typy planowania są używane do klasyfikowania harmonogramów kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="9cb90-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="9cb90-143">Na przykład można ustalić harmonogram kwestionariuszy do następujących celów:</span><span class="sxs-lookup"><span data-stu-id="9cb90-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="9cb90-144">Ocena</span><span class="sxs-lookup"><span data-stu-id="9cb90-144">Evaluation</span></span>
-   <span data-ttu-id="9cb90-145">Przegląd</span><span class="sxs-lookup"><span data-stu-id="9cb90-145">Survey</span></span>
-   <span data-ttu-id="9cb90-146">Testowanie</span><span class="sxs-lookup"><span data-stu-id="9cb90-146">Testing</span></span>

<span data-ttu-id="9cb90-147">Na stronie **harmonogramów kwestionariuszy** można określić typy planowania dla harmonogramu kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="9cb90-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="9cb90-148">Typy odwołań do kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="9cb90-148">Reference types for questionnaire</span></span>

<span data-ttu-id="9cb90-149">Typy odwołań służą do wprowadzania kryteriów dla respondentów, które można wybrać podczas planowania kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="9cb90-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="9cb90-150">Użyj strony **typy odwołań** do skonfigurowania odwołań do kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="9cb90-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="9cb90-151">Każdy typ odwołania odpowiada tabeli w Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="9cb90-151">Each reference type corresponds to a table in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="9cb90-152">Podczas tworzenia harmonogramów kwestionariuszy można określić poszczególne rekordy w tabeli lub zakres rekordów, które będzie można skojarzyć z kwestionariuszem.</span><span class="sxs-lookup"><span data-stu-id="9cb90-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="9cb90-153">Na przykład zaznaczenie w tabeli kursów pozwala określić, do których kursów będzie się odnosić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="9cb90-154">Po skonfigurowaniu odwołanie do tabeli kursów, niektóre pola i przyciski na stronie **kursów** stają się dostępne.</span><span class="sxs-lookup"><span data-stu-id="9cb90-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="9cb90-155">Harmonogramy kwestionariuszy</span><span class="sxs-lookup"><span data-stu-id="9cb90-155">Questionnaire schedules</span></span>

<span data-ttu-id="9cb90-156">Harmonogramy kwestionariuszy służą do generowania wielu planowanych sesji odpowiedzi dla grupy użytkowników, na podstawie typu odwołania.</span><span class="sxs-lookup"><span data-stu-id="9cb90-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="9cb90-157">Utwórz harmonogram na stronie **Harmonogramy kwestionariuszy**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="9cb90-158">Wybierz typ planowania, aby skategoryzować harmonogram, a także wybierz typ odwołania, które powinno być używane do zapytań o konkretnych użytkowników systemu.</span><span class="sxs-lookup"><span data-stu-id="9cb90-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="9cb90-159">Na przykład jeśli wybierzesz typ odwołania do tabeli kursów, możesz wybrać określony kurs w polu **Odwołanie**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="9cb90-160">Kliknij **Szczegóły ustawień**, aby wybrać kwestionariusz i inne kryteria.</span><span class="sxs-lookup"><span data-stu-id="9cb90-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="9cb90-161">Na przykład można określić imię i nazwisko instruktora jako kryterium, jeśli kwestionariusz służy do oceny instruktora.</span><span class="sxs-lookup"><span data-stu-id="9cb90-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="9cb90-162">Po zakończeniu wprowadzania szczegółów konfiguracji system generuje zaplanowane sesje odpowiedzi dla użytkowników, którzy są uwzględnieni w zapytaniu.</span><span class="sxs-lookup"><span data-stu-id="9cb90-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="9cb90-163">Kliknij **Zaplanowane sesje odpowiedzi** w celu wyświetlania sesji odpowiedzi dla harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="9cb90-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="9cb90-164">Można ręcznie utworzyć dodatkowe planowane sesje odpowiedzi lub usunąć planowane sesje odpowiedzi, które nie otrzymały odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9cb90-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="9cb90-165">Kliknij kolejno opcje **Funkcje** &gt; **Start**, aby udostępnić kwestionariusz użytkownikom w powiązanych zaplanowanych sesjach odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9cb90-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="9cb90-166">Kliknij **Odpowiedzi** w celu wyświetlania odpowiedzi z wypełnionych kwestionariuszy.</span><span class="sxs-lookup"><span data-stu-id="9cb90-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="9cb90-167">Opcjonalnie można skopiować ustawienia harmonogramu kwestionariusza, zaplanowanych sesji odpowiedzi i odpowiedzi do nowego harmonogramu kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="9cb90-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="9cb90-168">Powiadamianie respondentów o kwestionariuszach, które są dla nich dostępne</span><span class="sxs-lookup"><span data-stu-id="9cb90-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="9cb90-169">Gdy rozprowadzasz kwestionariusz, musisz powiadomić respondentów, że kwestionariusze są dla nich dostępne.</span><span class="sxs-lookup"><span data-stu-id="9cb90-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="9cb90-170">Powiadamianie respondentów o planowanej sesji odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="9cb90-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="9cb90-171">Jeśli używasz planowanej sesji odpowiedzi, należy powiadomić wybraną osobę bezpośrednio, np. telefoniczne lub e-mailem.</span><span class="sxs-lookup"><span data-stu-id="9cb90-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="9cb90-172">Powiadamianie respondentów o planowaniu</span><span class="sxs-lookup"><span data-stu-id="9cb90-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="9cb90-173">Na stronie **Harmonogramy kwestionariuszy** można przygotować i wysłać wiadomość e-mail do wszystkich respondentów przypisanych do danego kwestionariusza.</span><span class="sxs-lookup"><span data-stu-id="9cb90-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="9cb90-174">Wprowadź tekst wiadomości e-mail na karcie **Wiadomość e-mail samoobsługi pracownika**. Po rozpoczęciu harmonogramu kliknij opcję **Funkcje** &gt; **Wyślij wiadomość e-mail**, aby wygenerować i wysłać wiadomość e-mail do osób udzielających odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9cb90-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="9cb90-175">Respondenci mogą następnie zalogować się w witrynie i wypełnić kwestionariusz.</span><span class="sxs-lookup"><span data-stu-id="9cb90-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> [!NOTE]
> <span data-ttu-id="9cb90-176">Zanim będzie można skorzystać z funkcji poczty e-mail, administrator IT musi wprowadzić ustawienia poczty e-mail na stronie **Parametry poczty e-mail**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-176">Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="9cb90-177">Kończenie planowanego arkusza</span><span class="sxs-lookup"><span data-stu-id="9cb90-177">Ending a scheduled questionnaire</span></span>

<span data-ttu-id="9cb90-178">Można zakończyć zaplanowany kwestionariusz po ukończeniu przez wszystkich respondentów przypisanych do nich sesji odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="9cb90-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="9cb90-179">Po zakończeniu zaplanowanego kwestionariusza, nie można skopiować jego ustawień do nowego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="9cb90-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> [!NOTE]
>   <span data-ttu-id="9cb90-180">Jeśli co najmniej jeden respondent nie wypełnił kwestionariusza, a mimo to planowanie ma zostać zakończone, najpierw usuń odpowiednich respondentów z listy na stronie **Planowana sesja odpowiedzi**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-180">If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="9cb90-181">Po wykonaniu tej czynności będzie można zakończyć planowanie.</span><span class="sxs-lookup"><span data-stu-id="9cb90-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="9cb90-182">Wypełnianie kwestionariusza</span><span class="sxs-lookup"><span data-stu-id="9cb90-182">Completing questionnaires</span></span>

<span data-ttu-id="9cb90-183">Po zaprojektowaniu i rozesłaniu kwestionariusza, kwestionariusz może zostać wypełniony przez wybranych respondentów.</span><span class="sxs-lookup"><span data-stu-id="9cb90-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="9cb90-184">Kwestionariusze można wypełniać w dwóch lokalizacjach:</span><span class="sxs-lookup"><span data-stu-id="9cb90-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="9cb90-185">W okienku nawigacji kliknij kolejno opcje **Kwestionariusze** &gt; **Dystrybuuj** &gt; **Wypełnianie kwestionariusza**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="9cb90-186">W obszarze Samoobsługa pracownika etatowego kliknij **Kwestionariusze do wypełnienia**.</span><span class="sxs-lookup"><span data-stu-id="9cb90-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="9cb90-187">Kwestionariusze można udostępnić wszystkich osobom w sieci, określonym użytkownikom lub grupom użytkowników.</span><span class="sxs-lookup"><span data-stu-id="9cb90-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>


