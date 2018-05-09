---
title: "Konfigurowanie zadania ręcznego w przepływie pracy"
description: "W tym temacie wyjaśniono sposób konfigurowania właściwości zadania ręcznego."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b2bdfb2f0f527c4f9b14f37c3a55fcdc3c0605f7
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="configure-a-manual-task-in-a-workflow"></a><span data-ttu-id="8ec3e-103">Konfigurowanie zadania ręcznego w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-103">Configure a manual task in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ec3e-104">W tym temacie wyjaśniono sposób konfigurowania właściwości zadania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-104">This topic explains how to configure the properties for a manual task.</span></span>

<span data-ttu-id="8ec3e-105">Aby skonfigurować zadanie ręczne, w edytorze przepływu pracy kliknij zadanie prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-105">To configure a manual task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="8ec3e-106">Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości zadania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-106">Then use the following procedures to configure the properties for the manual task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="8ec3e-107">Nadawanie nazwy zadaniu</span><span class="sxs-lookup"><span data-stu-id="8ec3e-107">Name the task</span></span>
<span data-ttu-id="8ec3e-108">Wykonaj następujące kroki, aby wprowadzić nazwę zadania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-108">Follow these steps to enter a name for the manual task.</span></span>

1.  <span data-ttu-id="8ec3e-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="8ec3e-110">W polu **Nazwa** wprowadź unikatową nazwę zadania.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="8ec3e-111">Wprowadzanie wiersza tematu i instrukcji</span><span class="sxs-lookup"><span data-stu-id="8ec3e-111">Enter a subject line and instructions</span></span>
<span data-ttu-id="8ec3e-112">Należy wprowadzić wiersz tematu i instrukcje dla użytkowników przypisanych do zadania.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-112">You must provide a subject line and instructions to users who are assigned to the task.</span></span> <span data-ttu-id="8ec3e-113">Na przykład jeśli konfigurujesz zadanie dla zapotrzebowań na zakup, użytkownik przypisany do zadania zobaczy wiersz tematu i instrukcje na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-113">For example, if you're configuring a task for purchase requisitions, the user who is assigned to the task sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="8ec3e-114">Wiersz tematu pojawia się na pasku komunikatów na stronie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="8ec3e-115">Może wtedy kliknąć ikonę na pasku komunikatów i przeczytać instrukcje.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="8ec3e-116">Aby wprowadzić wiersz tematu i instrukcje, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-116">Follow these steps to enter a subject line and instructions.</span></span>

1.  <span data-ttu-id="8ec3e-117">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-117">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="8ec3e-118">W polu **Temat elementu pracy** wprowadź wiersz tematu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-118">In the **Work item subject** field, enter the subject line.</span></span>
3.  <span data-ttu-id="8ec3e-119">Aby spersonalizować wiersz tematu, można wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="8ec3e-120">Podczas wyświetlania wiersza tematu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="8ec3e-121">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-121">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="8ec3e-122">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-122">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="8ec3e-123">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-123">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="8ec3e-124">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-124">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="8ec3e-125">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-125">Click **Insert**.</span></span>

4.  <span data-ttu-id="8ec3e-126">Aby dodać tłumaczenia wiersza tematu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-126">To add translations of the subject line, follow these steps:</span></span>
    1.  <span data-ttu-id="8ec3e-127">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-127">Click **Translations**.</span></span>
    2.  <span data-ttu-id="8ec3e-128">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-128">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="8ec3e-129">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="8ec3e-130">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-130">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="8ec3e-131">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6.  <span data-ttu-id="8ec3e-132">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-132">Click **Close**.</span></span>

5.  <span data-ttu-id="8ec3e-133">W polu **Instrukcje dotyczące elementu produkcyjnego** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-133">In the **Work item instructions** field, enter the instructions.</span></span>
6.  <span data-ttu-id="8ec3e-134">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="8ec3e-135">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="8ec3e-136">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-136">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="8ec3e-137">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-137">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="8ec3e-138">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-138">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="8ec3e-139">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-139">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="8ec3e-140">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-140">Click **Insert**.</span></span>

7.  <span data-ttu-id="8ec3e-141">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-141">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="8ec3e-142">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-142">Click **Translations**.</span></span>
    2.  <span data-ttu-id="8ec3e-143">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-143">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="8ec3e-144">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="8ec3e-145">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-145">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="8ec3e-146">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 6.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6.  <span data-ttu-id="8ec3e-147">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-147">Click **Close**.</span></span>

## <a name="assign-the-task"></a><span data-ttu-id="8ec3e-148">Przypisywanie zadania</span><span class="sxs-lookup"><span data-stu-id="8ec3e-148">Assign the task</span></span>
<span data-ttu-id="8ec3e-149">Wykonaj poniższe kroki, aby określić, komu ma zostać przypisane to zadanie ręczne.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-149">Follow these steps to specify who the manual task should be assigned to.</span></span>

1.  <span data-ttu-id="8ec3e-150">W lewym okienku kliknij opcję **Przypisanie**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-150">In the left pane, click **Assignment**.</span></span>
2.  <span data-ttu-id="8ec3e-151">Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 3.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8ec3e-152">Opcja</span><span class="sxs-lookup"><span data-stu-id="8ec3e-152">Option</span></span></th>
    <th><span data-ttu-id="8ec3e-153">Użytkownicy, którym jest przypisane zadanie</span><span class="sxs-lookup"><span data-stu-id="8ec3e-153">Users that the task is assigned to</span></span></th>
    <th><span data-ttu-id="8ec3e-154">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="8ec3e-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-155">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="8ec3e-155">Participant</span></span></td>
    <td><span data-ttu-id="8ec3e-156">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="8ec3e-156">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-157">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której ma zostać przypisane zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the task to.</span></span></li>
    <li><span data-ttu-id="8ec3e-158">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której ma zostać przypisane zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-158">In the <strong>Participant</strong> list, select the group or role to assign the task to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="8ec3e-159">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="8ec3e-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="8ec3e-160">Użytkownicy w określonej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="8ec3e-160">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-161">Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać przypisane zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the task to.</span></span></li>
    <li><span data-ttu-id="8ec3e-162">System musi pobrać zakres nazwisk użytkowników z hierarchii.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="8ec3e-163">Te nazwy reprezentują użytkowników, którym można przypisać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-163">These names represent users that the task can be assigned to.</span></span> <span data-ttu-id="8ec3e-164">Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="8ec3e-165">Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="8ec3e-166">Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="8ec3e-167">Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="8ec3e-168">Na karcie <strong>Opcje hierarchii</strong> określ, którym użytkownikom w zakresie należy przypisać zadanie:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="8ec3e-169"><strong>Przypisz do wszystkich pobranych użytkowników</strong> — zadanie zostanie przypisane do wszystkich użytkowników w zakresie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-169"><strong>Assign to all users retrieved</strong> – The task is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="8ec3e-170"><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — zadanie zostanie przypisane tylko do ostatniego użytkownika w zakresie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-170"><strong>Assign only to last user retrieved</strong> – The task is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="8ec3e-171"><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — zadanie nie zostanie przypisane użytkownikom w zakresie, którzy spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-171"><strong>Exclude users with the following condition</strong> – The task isn't assigned to users in the range who meet a specific condition.</span></span> <span data-ttu-id="8ec3e-172">Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-173">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-173">Workflow user</span></span></td>
    <td><span data-ttu-id="8ec3e-174">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-174">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="8ec3e-175">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="8ec3e-176">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="8ec3e-176">User</span></span></td>
    <td><span data-ttu-id="8ec3e-177">Konkretny użytkownik programu Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8ec3e-177">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-178">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="8ec3e-179">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-179">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="8ec3e-180">Wybierz użytkowników, którym chcesz przypisać zadanie, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-180">Select the users to assign the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-181">Kolejka</span><span class="sxs-lookup"><span data-stu-id="8ec3e-181">Queue</span></span></td>
    <td><span data-ttu-id="8ec3e-182">Kolejka elementów roboczych</span><span class="sxs-lookup"><span data-stu-id="8ec3e-182">A work item queue</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-183">Po wybraniu wartości w polu <strong>Kolejka</strong> kliknij kartę <strong>Na podstawie kolejki</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-183">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="8ec3e-184">Aby przypisać zadanie do określonej kolejki, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-184">To assign the task to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="8ec3e-185">Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Kolejki elementów roboczych</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-185">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="8ec3e-186">Na liście <strong>Nazwa kolejki</strong> zaznacz kolejkę.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-186">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="8ec3e-187">Jeśli określony warunek ma decydować o kolejce, do której zostanie przypisane zadanie, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-187">If a specific condition should determine which queue the task is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="8ec3e-188">Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Warunkowe kolejki elementów roboczych</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-188">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="8ec3e-189">Na liście <strong>Nazwa kolejki</strong> zaznacz pozycję <strong>Kolejka warunkowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-189">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol></li>
    </ol><span data-ttu-id="8ec3e-190">
    <strong>Uwaga:</strong> Ta opcja jest używana tylko do niektórych przepływów pracy, takich jak Zarządzanie sprawami.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-190">
    <strong>Note:</strong> This option is used for only a few workflows, such as Case management.</span></span></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="8ec3e-191">Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na wykonanie zadania.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-191">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="8ec3e-192">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-192">Select one of the following options:</span></span>
    -   <span data-ttu-id="8ec3e-193">**Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-193">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="8ec3e-194">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-194">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="8ec3e-195">**Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-195">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="8ec3e-196">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-196">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="8ec3e-197">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-197">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    -   <span data-ttu-id="8ec3e-198">**Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-198">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="8ec3e-199">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-199">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="8ec3e-200">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-200">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="8ec3e-201">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-201">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

    <span data-ttu-id="8ec3e-202">Jeśli użytkownik nie wykona zadania w wyznaczonym czasie, staje się ono zaległe.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-202">If the user doesn't complete the task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="8ec3e-203">Zadanie zaległe można eskalować na podstawie opcji wybranych na stronie w obszarze **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-203">A task that is overdue can be escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-the-task-is-overdue"></a><span data-ttu-id="8ec3e-204">Określanie, co się dzieje z zadaniem zaległym</span><span class="sxs-lookup"><span data-stu-id="8ec3e-204">Specify what happens when the task is overdue</span></span>
<span data-ttu-id="8ec3e-205">Jeśli użytkownik nie wykona zadania ręcznego w wyznaczonym czasie, staje się ono zaległe.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-205">If a user doesn't complete the manual task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="8ec3e-206">Zadanie zaległe może być eskalowane lub automatycznie przypisywane do innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-206">A task that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="8ec3e-207">Wykonaj następujące kroki, eskalować zaległe zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-207">Follow these steps to escalate the task if it's overdue.</span></span>

1.  <span data-ttu-id="8ec3e-208">W lewym okienku kliknij opcję **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-208">In the left pane, click **Escalation**.</span></span>
2.  <span data-ttu-id="8ec3e-209">Zaznacz pole wyboru **Użyj ścieżki eskalacji**, aby utworzyć ścieżkę eskalacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-209">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="8ec3e-210">System automatycznie przypisze zadanie do użytkowników wymienionych w ścieżce eskalacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-210">The system automatically assigns the task to the users who are listed in the escalation path.</span></span> <span data-ttu-id="8ec3e-211">Na przykład poniższa tabela przedstawia ścieżkę eskalacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-211">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="8ec3e-212">Kolejność</span><span class="sxs-lookup"><span data-stu-id="8ec3e-212">Sequence</span></span> | <span data-ttu-id="8ec3e-213">Ścieżka eskalacji</span><span class="sxs-lookup"><span data-stu-id="8ec3e-213">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="8ec3e-214">1 przypada na wpłatę z zysku na rzecz budżetu państwa</span><span class="sxs-lookup"><span data-stu-id="8ec3e-214">1</span></span>        | <span data-ttu-id="8ec3e-215">Przypisać do: Danuta</span><span class="sxs-lookup"><span data-stu-id="8ec3e-215">Assign to: Donna</span></span>     |
    | <span data-ttu-id="8ec3e-216">2</span><span class="sxs-lookup"><span data-stu-id="8ec3e-216">2</span></span>        | <span data-ttu-id="8ec3e-217">Przypisać do: Ireny</span><span class="sxs-lookup"><span data-stu-id="8ec3e-217">Assign to: Erin</span></span>      |
    | <span data-ttu-id="8ec3e-218">3</span><span class="sxs-lookup"><span data-stu-id="8ec3e-218">3</span></span>        | <span data-ttu-id="8ec3e-219">Działanie końcowe: Odrzucenie</span><span class="sxs-lookup"><span data-stu-id="8ec3e-219">Final action: Reject</span></span> |

    <span data-ttu-id="8ec3e-220">W tym przykładzie system przypisuje zaległe zadanie do Danuty.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-220">In this example, the system assigns the overdue task to Donna.</span></span> <span data-ttu-id="8ec3e-221">Jeśli Danuta nie wykona zadania w przydzielonym czasie, system przypisze zadanie do Ireny.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-221">If Donna doesn't complete the task in the allotted time, the system assigns the task to Erin.</span></span> <span data-ttu-id="8ec3e-222">Jeśli Irena nie wykona zadania w przydzielonym jej czasie, system odrzuci dokument przesłany do przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-222">If Erin doesn't complete the task in the allotted time, the system rejects the document that was submitted for processing.</span></span>
3.  <span data-ttu-id="8ec3e-223">Aby dodać użytkownika do ścieżki eskalacji, kliknij opcję **Dodaj eskalację**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-223">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="8ec3e-224">Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 4.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-224">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8ec3e-225">Opcja</span><span class="sxs-lookup"><span data-stu-id="8ec3e-225">Option</span></span></th>
    <th><span data-ttu-id="8ec3e-226">Użytkownicy, do których zadanie jest eskalowane</span><span class="sxs-lookup"><span data-stu-id="8ec3e-226">Users that the task is escalated to</span></span></th>
    <th><span data-ttu-id="8ec3e-227">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="8ec3e-227">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-228">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="8ec3e-228">Hierarchy</span></span></td>
    <td><span data-ttu-id="8ec3e-229">Użytkownicy w określonej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="8ec3e-229">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-230">Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać eskalowane zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-230">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the task to.</span></span></li>
    <li><span data-ttu-id="8ec3e-231">System musi pobrać zakres nazwisk użytkowników z hierarchii.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-231">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="8ec3e-232">Te nazwy reprezentują użytkowników, do których można eskalować zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-232">These names represent users that the task can be escalated to.</span></span> <span data-ttu-id="8ec3e-233">Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-233">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="8ec3e-234">Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-234">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="8ec3e-235">Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-235">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="8ec3e-236">Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-236">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="8ec3e-237">Na karcie <strong>Opcje hierarchii</strong> określ, do których użytkowników w zakresie należy eskalować zadanie:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-237">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="8ec3e-238"><strong>Przypisz do wszystkich pobranych użytkowników</strong> — zadanie zostanie eskalowane do wszystkich użytkowników w zakresie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-238"><strong>Assign to all users retrieved</strong> – The task is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="8ec3e-239"><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — zadanie zostanie eskalowane tylko do ostatniego użytkownika w zakresie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-239"><strong>Assign only to last user retrieved</strong> – The task is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="8ec3e-240"><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — to zadanie nie będzie eskalowane do użytkowników w zakresie, którzy spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-240"><strong>Exclude users with the following condition</strong> – This task isn't escalated to users in the range who meet a specific condition.</span></span> <span data-ttu-id="8ec3e-241">Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-241">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="8ec3e-242">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-242">Workflow user</span></span></td>
    <td><span data-ttu-id="8ec3e-243">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-243">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="8ec3e-244">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-244">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-245">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="8ec3e-245">User</span></span></td>
    <td><span data-ttu-id="8ec3e-246">Konkretny użytkownik programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8ec3e-246">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-247">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-247">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="8ec3e-248">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-248">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="8ec3e-249">Wybierz użytkowników, do których chcesz eskalować zadanie, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-249">Select the users to escalate the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  <span data-ttu-id="8ec3e-250">Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na wykonanie zadania.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-250">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="8ec3e-251">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-251">Select one of the following options:</span></span>
    -   <span data-ttu-id="8ec3e-252">**Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-252">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="8ec3e-253">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-253">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="8ec3e-254">**Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-254">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="8ec3e-255">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-255">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="8ec3e-256">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-256">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    -   <span data-ttu-id="8ec3e-257">**Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-257">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="8ec3e-258">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-258">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="8ec3e-259">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-259">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="8ec3e-260">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-260">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

5.  <span data-ttu-id="8ec3e-261">Powtórz kroki od 3 do 4 dla każdego użytkownika, który powinien zostać dodany do ścieżki eskalacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-261">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="8ec3e-262">Można zmienić kolejność użytkowników.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-262">You can change the order of the users.</span></span>
6.  <span data-ttu-id="8ec3e-263">Jeśli użytkownicy wymienieni w ścieżce eskalacji nie wykonają zadania w wyznaczonym czasie, system wykona na nim operację.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-263">If the users in the escalation path don't complete the task in the allotted time, the system takes action on the task.</span></span> <span data-ttu-id="8ec3e-264">Aby określić akcję podejmowaną przez system, wybierz wiersz **Akcja**, a następnie na karcie **Zakończ działanie** wybierz akcję.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-264">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a><span data-ttu-id="8ec3e-265">Określanie, kiedy system automatycznie wykonuje operację na zadaniu</span><span class="sxs-lookup"><span data-stu-id="8ec3e-265">Specify when the system automatically acts on the task</span></span>
<span data-ttu-id="8ec3e-266">Można skonfigurować system, aby podejmował akcję wobec zadania ręcznego, jeśli są spełnione określone warunki.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-266">You can configure the system to take action on the manual task if specific conditions are met.</span></span> <span data-ttu-id="8ec3e-267">Na przykład zadanie wymaga, aby członek działu raportów z wydatków przeglądał paragony dostarczane razem z raportem z wydatków.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-267">For example, a task requires that a member of the Expense reports department review the receipts that are submitted together with an expense report.</span></span> <span data-ttu-id="8ec3e-268">Zgodnie z zasadami firmy to zadanie trzeba wykonać, jeśli łączna kwota raportu z wydatków jest większa niż 100 USD.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-268">According to company policy, this task must be performed if the total amount of the expense report is more than USD 100.</span></span> <span data-ttu-id="8ec3e-269">W tym scenariuszu można tak skonfigurować system, aby automatycznie oznaczał zadanie jako **Ukończone**, gdy łączna kwota jest mniejsza niż 100.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-269">In this scenario, you can configure the system to automatically mark the task as **Complete** when the total amount is less than 100.</span></span> <span data-ttu-id="8ec3e-270">Wykonaj następujące kroki, aby określić, kiedy system podejmuje akcję wobec zadania ręcznego.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-270">Follow these steps to specify when the system takes action on the manual task.</span></span>

1.  <span data-ttu-id="8ec3e-271">W lewym okienku kliknij opcję **Akcje automatyczne**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-271">In the left pane, click **Automatic actions**.</span></span>
2.  <span data-ttu-id="8ec3e-272">Zaznacz pole wyboru **Włącz akcje automatyczne**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-272">Select the **Enable automatic actions** check box.</span></span>
3.  <span data-ttu-id="8ec3e-273">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-273">Click **Add condition**.</span></span>
4.  <span data-ttu-id="8ec3e-274">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-274">Enter a condition.</span></span>
5.  <span data-ttu-id="8ec3e-275">Wprowadź wszelkie wymagane dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-275">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="8ec3e-276">Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-276">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="8ec3e-277">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-277">Click **Test**.</span></span>
    2.  <span data-ttu-id="8ec3e-278">Na stronie **Warunek testowy przepływu pracy** w obszarze **Sprawdź poprawność warunku** wybierz rekord.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-278">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="8ec3e-279">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-279">Click **Test**.</span></span> <span data-ttu-id="8ec3e-280">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-280">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="8ec3e-281">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do strony **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-281">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

7.  <span data-ttu-id="8ec3e-282">Z listy **Akcja automatycznego ukończenia** wybierz akcję, jaką ma podjąć system wobec zadania.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-282">In the **Auto complete action** list, select the action that the system should take on the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="8ec3e-283">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="8ec3e-283">Specify when notifications are sent</span></span>
<span data-ttu-id="8ec3e-284">Możliwe jest wysyłanie do odpowiednich osób powiadomień w przypadku delegowania, eskalowania, ukończenia lub odrzucenia zadania ręcznego albo żądania jego modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-284">You can send notifications to people when a manual task has been delegated, escalated, completed, or rejected, or when a change has been requested.</span></span> <span data-ttu-id="8ec3e-285">Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-285">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1.  <span data-ttu-id="8ec3e-286">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-286">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="8ec3e-287">Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-287">Select the check box next to the events that notifications should be sent for:</span></span>
    -   <span data-ttu-id="8ec3e-288">**Deleguj** — zadanie zostało przypisane innemu użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-288">**Delegate** – The task has been assigned to another user.</span></span>
    -   <span data-ttu-id="8ec3e-289">**Eskaluj** — przypisany użytkownik nie wykonał zadania w wyznaczonym czasie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-289">**Escalate** – The assigned user hasn't completed the task in the allotted time.</span></span>
    -   <span data-ttu-id="8ec3e-290">**Ukończono** — przypisany użytkownik wykonał zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-290">**Complete** – The assigned user has completed the task.</span></span>
    -   <span data-ttu-id="8ec3e-291">**Odrzuć** — przypisany użytkownik odrzucił dokument, który został mu przesłany.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-291">**Reject** – The assigned user has rejected the document that was submitted.</span></span>
    -   <span data-ttu-id="8ec3e-292">**Żądanie zmiany** — przypisany użytkownik zażądał zmiany w przesłanym mu dokumencie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-292">**Request change** – The assigned user has requested a change to the document that was submitted.</span></span>

3.  <span data-ttu-id="8ec3e-293">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-293">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="8ec3e-294">Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-294">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5.  <span data-ttu-id="8ec3e-295">Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-295">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="8ec3e-296">Podczas wyświetlania powiadomień użytkownikom symbole zastępcze są zastępowane odpowiednimi informacjami.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-296">Placeholders are replaced with appropriate information when the notification is shown to users.</span></span> <span data-ttu-id="8ec3e-297">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-297">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="8ec3e-298">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-298">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="8ec3e-299">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-299">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="8ec3e-300">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-300">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="8ec3e-301">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-301">Click **Insert**.</span></span>

6.  <span data-ttu-id="8ec3e-302">Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-302">To add translations of the notification, follow these steps:</span></span>
    1.  <span data-ttu-id="8ec3e-303">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-303">Click **Translations**.</span></span>
    2.  <span data-ttu-id="8ec3e-304">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-304">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="8ec3e-305">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-305">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="8ec3e-306">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-306">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="8ec3e-307">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-307">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6.  <span data-ttu-id="8ec3e-308">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-308">Click **Close**.</span></span>

7.  <span data-ttu-id="8ec3e-309">Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-309">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="8ec3e-310">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-310">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8ec3e-311">Opcja</span><span class="sxs-lookup"><span data-stu-id="8ec3e-311">Option</span></span></th>
    <th><span data-ttu-id="8ec3e-312">Adresaci powiadomień</span><span class="sxs-lookup"><span data-stu-id="8ec3e-312">Notification recipients</span></span></th>
    <th><span data-ttu-id="8ec3e-313">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="8ec3e-313">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-314">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="8ec3e-314">Participant</span></span></td>
    <td><span data-ttu-id="8ec3e-315">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="8ec3e-315">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-316">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-316">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="8ec3e-317">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-317">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="8ec3e-318">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-318">Workflow user</span></span></td>
    <td><span data-ttu-id="8ec3e-319">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="8ec3e-319">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="8ec3e-320">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-320">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="8ec3e-321">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="8ec3e-321">User</span></span></td>
    <td><span data-ttu-id="8ec3e-322">Konkretny użytkownik programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8ec3e-322">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="8ec3e-323">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-323">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="8ec3e-324">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-324">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="8ec3e-325">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-325">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="8ec3e-326">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-326">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="8ec3e-327">Ustawianie limitu czasu</span><span class="sxs-lookup"><span data-stu-id="8ec3e-327">Set a time limit</span></span>
<span data-ttu-id="8ec3e-328">Jeśli zadanie ręczne musi zostać ukończone w określonym czasie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-328">Follow these steps if the manual task must be completed in a specific time.</span></span> 

<span data-ttu-id="8ec3e-329">**Uwaga:** Opcje wybranej w tej procedurze zastępują opcje wybrane na stronie w obszarach **Przypisanie** i **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-329">**Note:** The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1.  <span data-ttu-id="8ec3e-330">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-330">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="8ec3e-331">Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3.  <span data-ttu-id="8ec3e-332">W polu **Czas trwania** określ, do kiedy zadanie ma zostać ukończone.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-332">In the **Duration** field, specify when the task must be completed.</span></span> <span data-ttu-id="8ec3e-333">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="8ec3e-333">Select one of the following options:</span></span>
    -   <span data-ttu-id="8ec3e-334">**Godziny** — Wprowadź liczbę godzin, w ciągu których należy wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-334">**Hours** – Enter the number of hours that the task must be completed in.</span></span> <span data-ttu-id="8ec3e-335">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="8ec3e-336">**Dni** — Wprowadź liczbę dni, w ciągu których należy wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-336">**Days** – Enter the number of days that the task must be completed in.</span></span> <span data-ttu-id="8ec3e-337">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="8ec3e-338">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których należy wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-338">**Weeks** – Enter the number of weeks that the task must be completed in.</span></span>
    -   <span data-ttu-id="8ec3e-339">**Miesiące** — Wybierz dzień i tydzień, do kiedy należy wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-339">**Months** – Select the day and week that the task must be completed by.</span></span> <span data-ttu-id="8ec3e-340">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-340">For example, you might want the task to be completed by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="8ec3e-341">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy wykonać zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-341">**Years** – Select the day, week, and month that the task must be completed by.</span></span> <span data-ttu-id="8ec3e-342">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-342">For example, you might want the task to be completed by Friday of the third week of December.</span></span>

4.  <span data-ttu-id="8ec3e-343">W przypadku przekroczenia tego limitu czasu system wykona operację na zadaniu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-343">If the time limit is exceeded, the system takes action on the task.</span></span> <span data-ttu-id="8ec3e-344">Na liście **Akcja** zaznacz akcję, jaką ma podjąć system.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-344">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="8ec3e-345">Określanie akcji dostępnych użytkownikowi</span><span class="sxs-lookup"><span data-stu-id="8ec3e-345">Specify which actions are available to the user</span></span>
<span data-ttu-id="8ec3e-346">Gdy zadanie ręczne zostanie przypisane użytkownikowi, musi on podjąć wobec niego działanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-346">When the manual task is assigned to a user, the user must take action on the task.</span></span> <span data-ttu-id="8ec3e-347">Wykonaj następujące kroki, aby określić, które akcje użytkownik może wykonywać na zadaniu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-347">Follow these steps to specify which actions the user can take on the task.</span></span> <span data-ttu-id="8ec3e-348">**Uwaga:** Dostępne akcje będą się różnić w zależności od projektu zadania.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-348">**Note:** The actions that are available vary, depending on the design of the task.</span></span>

1.  <span data-ttu-id="8ec3e-349">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-349">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="8ec3e-350">Zaznacz pole wyboru **Ukończono**, jeśli użytkownik ma mieć możliwość oznaczenia zadania statusem **Ukończono**.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-350">Select the **Complete** check box if the user should be able to mark the task as **Complete**.</span></span>
3.  <span data-ttu-id="8ec3e-351">Zaznacz pole wyboru **Odrzuć**, jeśli użytkownik ma mieć możliwość odrzucenia przesłanego mu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-351">Select the **Reject** check box if the user should be able to reject the document that was submitted.</span></span>
4.  <span data-ttu-id="8ec3e-352">Zaznacz pole wyboru **Żądanie zmiany**, jeśli użytkownik ma mieć możliwość zażądania zmian w przesłanym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-352">Select the **Request change** check box if the user should be able to request changes to the document that was submitted.</span></span>
5.  <span data-ttu-id="8ec3e-353">Zaznacz pole wyboru **Deleguj**, jeśli użytkownik ma mieć możliwość przypisania zadania do innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-353">Select the **Delegate** check box if the user should be able to assign the task to another user.</span></span>
6.  <span data-ttu-id="8ec3e-354">Zaznacz pole wyboru **Przypisz ponownie**, jeśli użytkownik ma mieć możliwość przypisania zadania innemu użytkownikowi w kolejce elementów roboczych.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-354">Select the **Reassign** check box if the user should be able to reassign the task to another user in the work item queue.</span></span>
7.  <span data-ttu-id="8ec3e-355">Zaznacz pole wyboru **Zwolnienie**, jeśli użytkownik ma mieć możliwość przypisania zadania do kolejki elementów roboczych.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-355">Select the **Release** check box if the user should be able to reassign the task to the work item queue.</span></span> <span data-ttu-id="8ec3e-356">Następnie inny użytkownik może wykonać to zadanie.</span><span class="sxs-lookup"><span data-stu-id="8ec3e-356">Another user can then complete the task.</span></span>





