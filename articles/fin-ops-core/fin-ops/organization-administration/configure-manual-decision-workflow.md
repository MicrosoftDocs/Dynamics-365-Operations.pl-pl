---
title: Konfigurowanie decyzji ręcznych w przepływie pracy
description: W tym temacie wyjaśniono sposób konfigurowania właściwości decyzji ręcznej.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d351facbce02355ddb4bdf91d43d9df561e4f3b5
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798860"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="16160-103">Konfigurowanie decyzji ręcznych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="16160-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16160-104">W tym temacie wyjaśniono sposób konfigurowania właściwości decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="16160-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="16160-105">Aby skonfigurować decyzję ręczną, w edytorze przepływu pracy kliknij decyzję ręczną prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="16160-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="16160-106">Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="16160-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="16160-107">Nazywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="16160-107">Name the decision</span></span>

<span data-ttu-id="16160-108">Wykonaj następujące kroki, aby wprowadzić nazwę decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="16160-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="16160-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="16160-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="16160-110">W polu **Nazwa** wprowadź unikatową nazwę decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="16160-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="16160-111">Wprowadzanie wiersza tematu i instrukcji</span><span class="sxs-lookup"><span data-stu-id="16160-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="16160-112">Należy wprowadzić wiersz tematu i instrukcje dla użytkowników przypisanych do decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="16160-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="16160-113">Na przykład jeśli konfigurujesz decyzję dla zapotrzebowań na zakup, użytkownik przypisany do decyzji zobaczy wiersz tematu i instrukcje na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="16160-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="16160-114">Wiersz tematu pojawia się na pasku komunikatów na stronie.</span><span class="sxs-lookup"><span data-stu-id="16160-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="16160-115">Może wtedy kliknąć ikonę na pasku komunikatów i przeczytać instrukcje.</span><span class="sxs-lookup"><span data-stu-id="16160-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="16160-116">Aby wprowadzić wiersz tematu i instrukcje, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="16160-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="16160-117">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="16160-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="16160-118">Na karcie **Instrukcje** w polu **Temat elementu pracy** wprowadź wiersz tematu.</span><span class="sxs-lookup"><span data-stu-id="16160-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="16160-119">Aby spersonalizować wiersz tematu, można wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="16160-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="16160-120">Podczas wyświetlania wiersza tematu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="16160-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="16160-121">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="16160-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="16160-122">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="16160-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="16160-123">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="16160-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="16160-124">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="16160-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="16160-125">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="16160-125">Click **Insert**.</span></span>

4. <span data-ttu-id="16160-126">Aby dodać tłumaczenia wiersza tematu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="16160-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="16160-127">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="16160-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="16160-128">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="16160-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="16160-129">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="16160-130">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="16160-131">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="16160-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="16160-132">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="16160-132">Click **Close**.</span></span>

5. <span data-ttu-id="16160-133">W polu **Instrukcje dotyczące elementu produkcyjnego** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="16160-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="16160-134">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="16160-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="16160-135">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="16160-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="16160-136">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="16160-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="16160-137">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="16160-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="16160-138">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="16160-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="16160-139">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="16160-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="16160-140">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="16160-140">Click **Insert**.</span></span>

7. <span data-ttu-id="16160-141">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="16160-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="16160-142">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="16160-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="16160-143">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="16160-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="16160-144">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="16160-145">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="16160-146">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 6.</span><span class="sxs-lookup"><span data-stu-id="16160-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="16160-147">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="16160-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="16160-148">Określanie możliwych wyników decyzji</span><span class="sxs-lookup"><span data-stu-id="16160-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="16160-149">Zazwyczaj gdy dokument jest przypisany do osoby podejmującej decyzje, osobie tej jest zadawane pytanie.</span><span class="sxs-lookup"><span data-stu-id="16160-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="16160-150">Odpowiedź na to pytanie brzmi zazwyczaj **Tak** lub **Nie** albo **Prawda** lub **Fałsz**.</span><span class="sxs-lookup"><span data-stu-id="16160-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="16160-151">Wykonaj następujące kroki, aby określić możliwe wyniki decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="16160-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="16160-152">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="16160-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="16160-153">Na karcie **Wyniki** w polu **Wynik 1** wprowadź nazwę wyniku lub opcji.</span><span class="sxs-lookup"><span data-stu-id="16160-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="16160-154">Aby dodać tłumaczenia wyniku, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="16160-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="16160-155">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="16160-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="16160-156">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="16160-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="16160-157">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="16160-158">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="16160-159">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="16160-159">Click **Close**.</span></span>

4. <span data-ttu-id="16160-160">W polu **Wynik 2** wprowadź nazwę wyniku lub opcji.</span><span class="sxs-lookup"><span data-stu-id="16160-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="16160-161">Aby dodać tłumaczenia wyniku, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="16160-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="16160-162">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="16160-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="16160-163">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="16160-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="16160-164">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="16160-165">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="16160-166">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="16160-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="16160-167">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="16160-167">Specify when notifications are sent</span></span>

<span data-ttu-id="16160-168">Można wysyłać powiadomienia do osób w momencie wprowadzenia decyzji, jej delegowania lub eskalowania.</span><span class="sxs-lookup"><span data-stu-id="16160-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="16160-169">Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="16160-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="16160-170">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="16160-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="16160-171">Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="16160-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="16160-172">**\[Wybór 1\]** — przypisany użytkownik wybrał opcję **\[Wybór 1\]**.</span><span class="sxs-lookup"><span data-stu-id="16160-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="16160-173">**\[Wybór 2\]** — przypisany użytkownik wybrał opcję **\[Wybór 2\]**.</span><span class="sxs-lookup"><span data-stu-id="16160-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="16160-174">**Delegowanie** — przypisany użytkownik przypisał decyzję innemu użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="16160-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="16160-175">**Eskaluj** — przypisany użytkownik nie podjął decyzji w wyznaczonym czasie.</span><span class="sxs-lookup"><span data-stu-id="16160-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="16160-176">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="16160-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="16160-177">Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="16160-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="16160-178">Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="16160-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="16160-179">Podczas wyświetlania powiadomienia użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="16160-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="16160-180">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="16160-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="16160-181">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="16160-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="16160-182">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="16160-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="16160-183">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="16160-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="16160-184">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="16160-184">Click **Insert**.</span></span>

6. <span data-ttu-id="16160-185">Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="16160-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="16160-186">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="16160-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="16160-187">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="16160-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="16160-188">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="16160-189">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="16160-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="16160-190">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.</span><span class="sxs-lookup"><span data-stu-id="16160-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="16160-191">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="16160-191">Click **Close**.</span></span>

7. <span data-ttu-id="16160-192">Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="16160-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="16160-193">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.</span><span class="sxs-lookup"><span data-stu-id="16160-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="16160-194">Opcja</span><span class="sxs-lookup"><span data-stu-id="16160-194">Option</span></span></th>
    <th><span data-ttu-id="16160-195">Adresaci powiadomień</span><span class="sxs-lookup"><span data-stu-id="16160-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="16160-196">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="16160-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="16160-197">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="16160-197">Participant</span></span></td>
    <td><span data-ttu-id="16160-198">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="16160-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-199">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="16160-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="16160-200">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="16160-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-201">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="16160-201">Workflow user</span></span></td>
    <td><span data-ttu-id="16160-202">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="16160-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="16160-203">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="16160-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-204">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="16160-204">User</span></span></td>
    <td><span data-ttu-id="16160-205">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="16160-205">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-206">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="16160-207">Lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="16160-207">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="16160-208">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="16160-209">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="16160-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="16160-210">Przypisywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="16160-210">Assign a decision</span></span>

<span data-ttu-id="16160-211">Wykonaj poniższe kroki, aby określić, komu ma zostać przypisana decyzja ręczna.</span><span class="sxs-lookup"><span data-stu-id="16160-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="16160-212">W lewym okienku kliknij opcję **Przypisanie**.</span><span class="sxs-lookup"><span data-stu-id="16160-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="16160-213">Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 3.</span><span class="sxs-lookup"><span data-stu-id="16160-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="16160-214">Opcja</span><span class="sxs-lookup"><span data-stu-id="16160-214">Option</span></span></th>
    <th><span data-ttu-id="16160-215">Użytkownicy, którym jest przypisana decyzja</span><span class="sxs-lookup"><span data-stu-id="16160-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="16160-216">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="16160-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="16160-217">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="16160-217">Participant</span></span></td>
    <td><span data-ttu-id="16160-218">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="16160-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-219">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której ma zostać przypisana decyzja.</span><span class="sxs-lookup"><span data-stu-id="16160-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="16160-220">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której ma zostać przypisana decyzja.</span><span class="sxs-lookup"><span data-stu-id="16160-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-221">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="16160-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="16160-222">Użytkownicy w określonej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="16160-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-223">Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać przypisana decyzja.</span><span class="sxs-lookup"><span data-stu-id="16160-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="16160-224">System musi pobrać zakres nazwisk użytkowników z hierarchii.</span><span class="sxs-lookup"><span data-stu-id="16160-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="16160-225">Te nazwy reprezentują użytkowników, którym można przypisać decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="16160-226">Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system:</span><span class="sxs-lookup"><span data-stu-id="16160-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="16160-227">Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="16160-228">Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="16160-229">Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</span><span class="sxs-lookup"><span data-stu-id="16160-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="16160-230">Na karcie <strong>Opcje hierarchii</strong> określ, którym użytkownikom w zakresie należy przypisać decyzję:</span><span class="sxs-lookup"><span data-stu-id="16160-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="16160-231"><strong>Przypisz do wszystkich pobranych użytkowników</strong> — decyzja zostanie przypisana do wszystkich użytkowników w zakresie.</span><span class="sxs-lookup"><span data-stu-id="16160-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="16160-232"><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — decyzja zostanie przypisana tylko do ostatniego użytkownika w zakresie.</span><span class="sxs-lookup"><span data-stu-id="16160-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="16160-233"><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — decyzja nie zostanie przypisana żadnym użytkownikom w zakresie, którzy spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="16160-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="16160-234">Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</span><span class="sxs-lookup"><span data-stu-id="16160-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-235">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="16160-235">Workflow user</span></span></td>
    <td><span data-ttu-id="16160-236">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="16160-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="16160-237">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="16160-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-238">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="16160-238">User</span></span></td>
    <td><span data-ttu-id="16160-239">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="16160-239">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-240">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="16160-241">Lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="16160-241">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="16160-242">Wybierz użytkowników, którym chcesz przypisać decyzję, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="16160-243">Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na podjęcie decyzji.</span><span class="sxs-lookup"><span data-stu-id="16160-243">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="16160-244">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="16160-244">Select one of the following options:</span></span>

    - <span data-ttu-id="16160-245">**Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-245">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="16160-246">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="16160-246">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="16160-247">**Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-247">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="16160-248">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="16160-248">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="16160-249">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-249">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="16160-250">**Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-250">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="16160-251">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="16160-251">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="16160-252">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-252">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="16160-253">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="16160-253">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="16160-254">Jeśli użytkownik nie podejmie decyzji w wyznaczonym czasie, staje się ona zaległa.</span><span class="sxs-lookup"><span data-stu-id="16160-254">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="16160-255">Decyzję zaległą można eskalować na podstawie opcji wybranych na stronie w obszarze **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="16160-255">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="16160-256">Określanie, co się dzieje z decyzją zaległą</span><span class="sxs-lookup"><span data-stu-id="16160-256">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="16160-257">Jeśli użytkownik nie podejmie decyzji w wyznaczonym czasie, staje się ona zaległa.</span><span class="sxs-lookup"><span data-stu-id="16160-257">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="16160-258">Decyzja zaległa może być eskalowana lub automatycznie przypisywana do innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="16160-258">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="16160-259">Wykonaj następujące kroki, aby eskalować zaległą decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-259">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="16160-260">W lewym okienku kliknij opcję **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="16160-260">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="16160-261">Zaznacz pole wyboru **Użyj ścieżki eskalacji**, aby utworzyć ścieżkę eskalacji.</span><span class="sxs-lookup"><span data-stu-id="16160-261">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="16160-262">System automatycznie przypisze decyzję do użytkowników wymienionych w ścieżce eskalacji.</span><span class="sxs-lookup"><span data-stu-id="16160-262">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="16160-263">Na przykład poniższa tabela przedstawia ścieżkę eskalacji.</span><span class="sxs-lookup"><span data-stu-id="16160-263">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="16160-264">Kolejność</span><span class="sxs-lookup"><span data-stu-id="16160-264">Sequence</span></span> | <span data-ttu-id="16160-265">Ścieżka eskalacji</span><span class="sxs-lookup"><span data-stu-id="16160-265">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="16160-266">1</span><span class="sxs-lookup"><span data-stu-id="16160-266">1</span></span>        | <span data-ttu-id="16160-267">Przypisać do: Danuta</span><span class="sxs-lookup"><span data-stu-id="16160-267">Assign to: Donna</span></span>           |
    | <span data-ttu-id="16160-268">2</span><span class="sxs-lookup"><span data-stu-id="16160-268">2</span></span>        | <span data-ttu-id="16160-269">Przypisać do: Ireny</span><span class="sxs-lookup"><span data-stu-id="16160-269">Assign to: Erin</span></span>            |
    | <span data-ttu-id="16160-270">3</span><span class="sxs-lookup"><span data-stu-id="16160-270">3</span></span>        | <span data-ttu-id="16160-271">Działanie końcowe: \[Wybór 1\]</span><span class="sxs-lookup"><span data-stu-id="16160-271">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="16160-272">W tym przykładzie system przypisuje zaległą decyzję do Danuty.</span><span class="sxs-lookup"><span data-stu-id="16160-272">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="16160-273">Jeśli Danuta nie podejmie decyzji w przydzielonym czasie, system przypisze decyzję do Ireny.</span><span class="sxs-lookup"><span data-stu-id="16160-273">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="16160-274">Jeśli Irena nie podejmie decyzji w przydzielonym czasie, system wybierze opcję **\[Wybór 1\]** jako decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-274">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="16160-275">Aby dodać użytkownika do ścieżki eskalacji, kliknij opcję **Dodaj eskalację**.</span><span class="sxs-lookup"><span data-stu-id="16160-275">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="16160-276">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 4.</span><span class="sxs-lookup"><span data-stu-id="16160-276">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="16160-277">Opcja</span><span class="sxs-lookup"><span data-stu-id="16160-277">Option</span></span></th>
    <th><span data-ttu-id="16160-278">Użytkownicy, do których decyzja jest eskalowana</span><span class="sxs-lookup"><span data-stu-id="16160-278">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="16160-279">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="16160-279">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="16160-280">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="16160-280">Hierarchy</span></span></td>
    <td><span data-ttu-id="16160-281">Użytkownicy w określonej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="16160-281">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-282">Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać eskalowana decyzja.</span><span class="sxs-lookup"><span data-stu-id="16160-282">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="16160-283">System musi pobrać zakres nazwisk użytkowników z hierarchii.</span><span class="sxs-lookup"><span data-stu-id="16160-283">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="16160-284">Te nazwy reprezentują użytkowników, do których można eskalować decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-284">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="16160-285">Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system:</span><span class="sxs-lookup"><span data-stu-id="16160-285">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="16160-286">Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-286">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="16160-287">Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-287">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="16160-288">Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</span><span class="sxs-lookup"><span data-stu-id="16160-288">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="16160-289">Na karcie <strong>Opcje hierarchii</strong> określ, do których użytkowników w zakresie należy eskalować decyzję:</span><span class="sxs-lookup"><span data-stu-id="16160-289">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="16160-290"><strong>Przypisz do wszystkich pobranych użytkowników</strong> — decyzja zostanie eskalowana do wszystkich użytkowników w zakresie.</span><span class="sxs-lookup"><span data-stu-id="16160-290"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="16160-291"><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — decyzja zostanie eskalowana tylko do ostatniego użytkownika w zakresie.</span><span class="sxs-lookup"><span data-stu-id="16160-291"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="16160-292"><strong>Nie uwzględniaj użytkowników spełniających następujący warunek:</strong> — decyzja nie będzie eskalowana do żadnych użytkowników w zakresie, którzy spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="16160-292"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="16160-293">Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</span><span class="sxs-lookup"><span data-stu-id="16160-293">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-294">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="16160-294">Workflow user</span></span></td>
    <td><span data-ttu-id="16160-295">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="16160-295">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="16160-296">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="16160-296">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="16160-297">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="16160-297">User</span></span></td>
    <td><span data-ttu-id="16160-298">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="16160-298">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="16160-299">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-299">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="16160-300">Lista <strong>Dostępni użytkownicy</strong> zawiera wszystkich użytkowników.</span><span class="sxs-lookup"><span data-stu-id="16160-300">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="16160-301">Wybierz użytkowników, do których chcesz eskalować decyzję, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="16160-301">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="16160-302">Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na podjęcie decyzji.</span><span class="sxs-lookup"><span data-stu-id="16160-302">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="16160-303">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="16160-303">Select one of the following options:</span></span>

    - <span data-ttu-id="16160-304">**Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-304">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="16160-305">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="16160-305">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="16160-306">**Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-306">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="16160-307">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="16160-307">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="16160-308">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-308">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="16160-309">**Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-309">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="16160-310">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="16160-310">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="16160-311">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-311">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="16160-312">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="16160-312">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="16160-313">Powtórz kroki od 3 do 4 dla każdego użytkownika, który powinien zostać dodany do ścieżki eskalacji.</span><span class="sxs-lookup"><span data-stu-id="16160-313">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="16160-314">Można zmienić kolejność użytkowników.</span><span class="sxs-lookup"><span data-stu-id="16160-314">You can change the order of the users.</span></span>
6. <span data-ttu-id="16160-315">Jeśli użytkownicy wymienieni w ścieżce eskalacji nie podejmą decyzji w wyznaczonym czasie, system sam podejmie decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-315">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="16160-316">Aby określić opcję wybieraną przez system, wybierz wiersz **Akcja**, a następnie na karcie **Zakończ działanie** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="16160-316">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="16160-317">Ustawianie limitu czasu</span><span class="sxs-lookup"><span data-stu-id="16160-317">Set a time limit</span></span>

<span data-ttu-id="16160-318">Jeśli decyzja musi zostać podjęta w określonym czasie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="16160-318">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="16160-319">Opcje wybranej w tej procedurze zastępują opcje wybrane na stronie w obszarach **Przypisanie** i **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="16160-319">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="16160-320">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="16160-320">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="16160-321">Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="16160-321">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="16160-322">W polu **Czas trwania** określ, do kiedy decyzja musi zostać podjęta.</span><span class="sxs-lookup"><span data-stu-id="16160-322">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="16160-323">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="16160-323">Select one of the following options:</span></span>

    - <span data-ttu-id="16160-324">**Godziny** — Wprowadź liczbę godzin.</span><span class="sxs-lookup"><span data-stu-id="16160-324">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="16160-325">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="16160-325">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="16160-326">**Dni** — Wprowadź liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="16160-326">**Days** – Enter the number of days.</span></span> <span data-ttu-id="16160-327">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="16160-327">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="16160-328">**Tygodnie** — Wprowadź liczbę tygodni.</span><span class="sxs-lookup"><span data-stu-id="16160-328">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="16160-329">**Miesiące** — Wybierz dzień i tydzień, do kiedy należy podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-329">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="16160-330">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="16160-330">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="16160-331">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-331">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="16160-332">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="16160-332">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="16160-333">W przypadku przekroczenia tego limitu czasu system sam podejmie decyzję.</span><span class="sxs-lookup"><span data-stu-id="16160-333">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="16160-334">Na liście **Akcja** zaznacz opcję, którą system powinien wybrać.</span><span class="sxs-lookup"><span data-stu-id="16160-334">In the **Action** list, select the option that the system should select.</span></span>
