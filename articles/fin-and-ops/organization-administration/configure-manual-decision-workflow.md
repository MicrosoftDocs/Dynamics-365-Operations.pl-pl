---
title: Konfigurowanie decyzji ręcznych w przepływie pracy
description: W tym temacie wyjaśniono sposób konfigurowania właściwości decyzji ręcznej.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d09e99a5bf99593a8fa7682f9d4f29eaa4e7c836
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569366"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="34497-103">Konfigurowanie decyzji ręcznych w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="34497-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34497-104">W tym temacie wyjaśniono sposób konfigurowania właściwości decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="34497-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="34497-105">Aby skonfigurować decyzję ręczną, w edytorze przepływu pracy kliknij decyzję ręczną prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarta strona **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="34497-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="34497-106">Następnie za pomocą procedur zamieszczonych niżej skonfiguruj właściwości decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="34497-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="34497-107">Nazywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="34497-107">Name the decision</span></span>

<span data-ttu-id="34497-108">Wykonaj następujące kroki, aby wprowadzić nazwę decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="34497-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="34497-109">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="34497-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="34497-110">W polu **Nazwa** wprowadź unikatową nazwę decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="34497-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="34497-111">Wprowadzanie wiersza tematu i instrukcji</span><span class="sxs-lookup"><span data-stu-id="34497-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="34497-112">Należy wprowadzić wiersz tematu i instrukcje dla użytkowników przypisanych do decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="34497-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="34497-113">Na przykład jeśli konfigurujesz decyzję dla zapotrzebowań na zakup, użytkownik przypisany do decyzji zobaczy wiersz tematu i instrukcje na stronie **Zapotrzebowania na zakup**.</span><span class="sxs-lookup"><span data-stu-id="34497-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="34497-114">Wiersz tematu pojawia się na pasku komunikatów na stronie.</span><span class="sxs-lookup"><span data-stu-id="34497-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="34497-115">Może wtedy kliknąć ikonę na pasku komunikatów i przeczytać instrukcje.</span><span class="sxs-lookup"><span data-stu-id="34497-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="34497-116">Aby wprowadzić wiersz tematu i instrukcje, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="34497-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="34497-117">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="34497-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="34497-118">Na karcie **Instrukcje** w polu **Temat elementu pracy** wprowadź wiersz tematu.</span><span class="sxs-lookup"><span data-stu-id="34497-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="34497-119">Aby spersonalizować wiersz tematu, można wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="34497-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="34497-120">Podczas wyświetlania wiersza tematu użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="34497-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="34497-121">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="34497-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="34497-122">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="34497-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="34497-123">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="34497-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="34497-124">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="34497-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="34497-125">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="34497-125">Click **Insert**.</span></span>

4. <span data-ttu-id="34497-126">Aby dodać tłumaczenia wiersza tematu, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="34497-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="34497-127">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="34497-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="34497-128">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="34497-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="34497-129">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="34497-130">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="34497-131">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="34497-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="34497-132">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="34497-132">Click **Close**.</span></span>

5. <span data-ttu-id="34497-133">W polu **Instrukcje dotyczące elementu produkcyjnego** wprowadź instrukcje.</span><span class="sxs-lookup"><span data-stu-id="34497-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="34497-134">Aby spersonalizować instrukcje, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="34497-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="34497-135">Podczas wyświetlania instrukcji użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="34497-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="34497-136">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="34497-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="34497-137">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="34497-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="34497-138">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="34497-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="34497-139">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="34497-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="34497-140">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="34497-140">Click **Insert**.</span></span>

7. <span data-ttu-id="34497-141">Aby dodać tłumaczenia instrukcji, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="34497-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="34497-142">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="34497-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="34497-143">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="34497-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="34497-144">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="34497-145">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="34497-146">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 6.</span><span class="sxs-lookup"><span data-stu-id="34497-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="34497-147">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="34497-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="34497-148">Określanie możliwych wyników decyzji</span><span class="sxs-lookup"><span data-stu-id="34497-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="34497-149">Zazwyczaj gdy dokument jest przypisany do osoby podejmującej decyzje, osobie tej jest zadawane pytanie.</span><span class="sxs-lookup"><span data-stu-id="34497-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="34497-150">Odpowiedź na to pytanie brzmi zazwyczaj **Tak** lub **Nie** albo **Prawda** lub **Fałsz**.</span><span class="sxs-lookup"><span data-stu-id="34497-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="34497-151">Wykonaj następujące kroki, aby określić możliwe wyniki decyzji ręcznej.</span><span class="sxs-lookup"><span data-stu-id="34497-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="34497-152">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="34497-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="34497-153">Na karcie **Wyniki** w polu **Wynik 1** wprowadź nazwę wyniku lub opcji.</span><span class="sxs-lookup"><span data-stu-id="34497-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="34497-154">Aby dodać tłumaczenia wyniku, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="34497-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="34497-155">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="34497-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="34497-156">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="34497-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="34497-157">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="34497-158">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="34497-159">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="34497-159">Click **Close**.</span></span>

4. <span data-ttu-id="34497-160">W polu **Wynik 2** wprowadź nazwę wyniku lub opcji.</span><span class="sxs-lookup"><span data-stu-id="34497-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="34497-161">Aby dodać tłumaczenia wyniku, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="34497-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="34497-162">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="34497-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="34497-163">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="34497-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="34497-164">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="34497-165">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="34497-166">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="34497-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="34497-167">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="34497-167">Specify when notifications are sent</span></span>

<span data-ttu-id="34497-168">Można wysyłać powiadomienia do osób w momencie wprowadzenia decyzji, jej delegowania lub eskalowania.</span><span class="sxs-lookup"><span data-stu-id="34497-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="34497-169">Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="34497-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="34497-170">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="34497-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="34497-171">Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="34497-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="34497-172">**\[Wybór 1\]** — przypisany użytkownik wybrał opcję **\[Wybór 1\]**.</span><span class="sxs-lookup"><span data-stu-id="34497-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="34497-173">**\[Wybór 2\]** — przypisany użytkownik wybrał opcję **\[Wybór 2\]**.</span><span class="sxs-lookup"><span data-stu-id="34497-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="34497-174">**Delegowanie** — przypisany użytkownik przypisał decyzję innemu użytkownikowi.</span><span class="sxs-lookup"><span data-stu-id="34497-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="34497-175">**Eskaluj** — przypisany użytkownik nie podjął decyzji w wyznaczonym czasie.</span><span class="sxs-lookup"><span data-stu-id="34497-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="34497-176">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="34497-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="34497-177">Na karcie **Tekst powiadomienia** w polu tekstowym wprowadź tekst powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="34497-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="34497-178">Aby spersonalizować powiadomienie, możesz wstawić symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="34497-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="34497-179">Podczas wyświetlania powiadomienia użytkownikom symbole zastępcze są zastępowane odpowiednimi danymi.</span><span class="sxs-lookup"><span data-stu-id="34497-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="34497-180">Wykonaj następujące czynności, aby wstawić symbol zastępczy:</span><span class="sxs-lookup"><span data-stu-id="34497-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="34497-181">W polu tekstowym kliknij miejsce, gdzie symbol zastępczy ma być wyświetlany.</span><span class="sxs-lookup"><span data-stu-id="34497-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="34497-182">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="34497-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="34497-183">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="34497-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="34497-184">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="34497-184">Click **Insert**.</span></span>

6. <span data-ttu-id="34497-185">Aby dodać tłumaczenia powiadomienia, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="34497-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="34497-186">Kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="34497-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="34497-187">Na wyświetlonej stronie kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="34497-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="34497-188">Z wyświetlonej listy wybierz język, w którym wprowadzasz tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="34497-189">W polu **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="34497-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="34497-190">Aby spersonalizować tekst, możesz wstawić symbole zastępcze, jak opisano w kroku 5.</span><span class="sxs-lookup"><span data-stu-id="34497-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="34497-191">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="34497-191">Click **Close**.</span></span>

7. <span data-ttu-id="34497-192">Na karcie **Odbiorcy** określ, komu będą wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="34497-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="34497-193">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 8.</span><span class="sxs-lookup"><span data-stu-id="34497-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="34497-194">Opcja</span><span class="sxs-lookup"><span data-stu-id="34497-194">Option</span></span></th>
    <th><span data-ttu-id="34497-195">Adresaci powiadomień</span><span class="sxs-lookup"><span data-stu-id="34497-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="34497-196">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="34497-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="34497-197">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="34497-197">Participant</span></span></td>
    <td><span data-ttu-id="34497-198">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="34497-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-199">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="34497-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="34497-200">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="34497-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-201">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="34497-201">Workflow user</span></span></td>
    <td><span data-ttu-id="34497-202">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="34497-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="34497-203">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="34497-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-204">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="34497-204">User</span></span></td>
    <td><span data-ttu-id="34497-205">Określeni użytkownicy Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="34497-205">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-206">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="34497-207">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="34497-207">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="34497-208">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="34497-209">Powtórz kroki od 3 do 7 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="34497-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="34497-210">Przypisywanie decyzji</span><span class="sxs-lookup"><span data-stu-id="34497-210">Assign a decision</span></span>

<span data-ttu-id="34497-211">Wykonaj poniższe kroki, aby określić, komu ma zostać przypisana decyzja ręczna.</span><span class="sxs-lookup"><span data-stu-id="34497-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="34497-212">W lewym okienku kliknij opcję **Przypisanie**.</span><span class="sxs-lookup"><span data-stu-id="34497-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="34497-213">Na karcie **Typ przypisania** wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 3.</span><span class="sxs-lookup"><span data-stu-id="34497-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="34497-214">Opcja</span><span class="sxs-lookup"><span data-stu-id="34497-214">Option</span></span></th>
    <th><span data-ttu-id="34497-215">Użytkownicy, którym jest przypisana decyzja</span><span class="sxs-lookup"><span data-stu-id="34497-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="34497-216">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="34497-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="34497-217">Uczestnik</span><span class="sxs-lookup"><span data-stu-id="34497-217">Participant</span></span></td>
    <td><span data-ttu-id="34497-218">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="34497-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-219">Gdy wybierzesz wartość w polu <strong>Uczestnik</strong>, na karcie <strong>Oparte na roli</strong> na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub roli, do której ma zostać przypisana decyzja.</span><span class="sxs-lookup"><span data-stu-id="34497-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="34497-220">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której ma zostać przypisana decyzja.</span><span class="sxs-lookup"><span data-stu-id="34497-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-221">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="34497-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="34497-222">Użytkownicy w określonej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="34497-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-223">Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać przypisana decyzja.</span><span class="sxs-lookup"><span data-stu-id="34497-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="34497-224">System musi pobrać zakres nazwisk użytkowników z hierarchii.</span><span class="sxs-lookup"><span data-stu-id="34497-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="34497-225">Te nazwy reprezentują użytkowników, którym można przypisać decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="34497-226">Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system:</span><span class="sxs-lookup"><span data-stu-id="34497-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="34497-227">Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="34497-228">Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="34497-229">Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</span><span class="sxs-lookup"><span data-stu-id="34497-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="34497-230">Na karcie <strong>Opcje hierarchii</strong> określ, którym użytkownikom w zakresie należy przypisać decyzję:</span><span class="sxs-lookup"><span data-stu-id="34497-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="34497-231"><strong>Przypisz do wszystkich pobranych użytkowników</strong> — decyzja zostanie przypisana do wszystkich użytkowników w zakresie.</span><span class="sxs-lookup"><span data-stu-id="34497-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="34497-232"><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — decyzja zostanie przypisana tylko do ostatniego użytkownika w zakresie.</span><span class="sxs-lookup"><span data-stu-id="34497-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="34497-233"><strong>Nie uwzględniaj użytkowników spełniających następujący warunek</strong> — decyzja nie zostanie przypisana żadnym użytkownikom w zakresie, którzy spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="34497-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="34497-234">Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</span><span class="sxs-lookup"><span data-stu-id="34497-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-235">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="34497-235">Workflow user</span></span></td>
    <td><span data-ttu-id="34497-236">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="34497-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="34497-237">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="34497-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-238">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="34497-238">User</span></span></td>
    <td><span data-ttu-id="34497-239">Konkretny użytkownik programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="34497-239">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-240">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="34497-241">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="34497-241">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="34497-242">Wybierz użytkowników, którym chcesz przypisać decyzję, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-243">Kolejka</span><span class="sxs-lookup"><span data-stu-id="34497-243">Queue</span></span></td>
    <td><span data-ttu-id="34497-244">Kolejka elementów roboczych</span><span class="sxs-lookup"><span data-stu-id="34497-244">A work item queue</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-245">Po wybraniu wartości w polu <strong>Kolejka</strong> kliknij kartę <strong>Na podstawie kolejki</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-245">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="34497-246">Aby przypisać decyzję do określonej kolejki, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="34497-246">To assign the decision to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="34497-247">Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Kolejki elementów roboczych</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-247">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="34497-248">Na liście <strong>Nazwa kolejki</strong> zaznacz kolejkę.</span><span class="sxs-lookup"><span data-stu-id="34497-248">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="34497-249">Jeśli określony warunek ma decydować o kolejce, do której zostanie przypisana decyzja, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="34497-249">If a specific condition should determine which queue the decision is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="34497-250">Na liście <strong>Typ kolejki</strong> zaznacz pozycję <strong>Warunkowe kolejki elementów roboczych</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-250">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="34497-251">Na liście <strong>Nazwa kolejki</strong> zaznacz pozycję <strong>Kolejka warunkowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-251">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] <span data-ttu-id="34497-252">Ta opcja jest używana tylko do niektórych przepływów pracy, takich jak Zarządzanie sprawami.</span><span class="sxs-lookup"><span data-stu-id="34497-252">This option is used for only a few workflows, such as Case management.</span></span></blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="34497-253">Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na podjęcie decyzji.</span><span class="sxs-lookup"><span data-stu-id="34497-253">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="34497-254">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="34497-254">Select one of the following options:</span></span>

    - <span data-ttu-id="34497-255">**Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-255">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="34497-256">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="34497-256">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="34497-257">**Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-257">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="34497-258">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="34497-258">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="34497-259">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-259">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="34497-260">**Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-260">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="34497-261">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="34497-261">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="34497-262">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-262">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="34497-263">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="34497-263">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="34497-264">Jeśli użytkownik nie podejmie decyzji w wyznaczonym czasie, staje się ona zaległa.</span><span class="sxs-lookup"><span data-stu-id="34497-264">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="34497-265">Decyzję zaległą można eskalować na podstawie opcji wybranych na stronie w obszarze **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="34497-265">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="34497-266">Określanie, co się dzieje z decyzją zaległą</span><span class="sxs-lookup"><span data-stu-id="34497-266">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="34497-267">Jeśli użytkownik nie podejmie decyzji w wyznaczonym czasie, staje się ona zaległa.</span><span class="sxs-lookup"><span data-stu-id="34497-267">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="34497-268">Decyzja zaległa może być eskalowana lub automatycznie przypisywana do innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="34497-268">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="34497-269">Wykonaj następujące kroki, aby eskalować zaległą decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-269">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="34497-270">W lewym okienku kliknij opcję **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="34497-270">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="34497-271">Zaznacz pole wyboru **Użyj ścieżki eskalacji**, aby utworzyć ścieżkę eskalacji.</span><span class="sxs-lookup"><span data-stu-id="34497-271">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="34497-272">System automatycznie przypisze decyzję do użytkowników wymienionych w ścieżce eskalacji.</span><span class="sxs-lookup"><span data-stu-id="34497-272">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="34497-273">Na przykład poniższa tabela przedstawia ścieżkę eskalacji.</span><span class="sxs-lookup"><span data-stu-id="34497-273">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="34497-274">Kolejność</span><span class="sxs-lookup"><span data-stu-id="34497-274">Sequence</span></span> | <span data-ttu-id="34497-275">Ścieżka eskalacji</span><span class="sxs-lookup"><span data-stu-id="34497-275">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="34497-276">1</span><span class="sxs-lookup"><span data-stu-id="34497-276">1</span></span>        | <span data-ttu-id="34497-277">Przypisać do: Danuta</span><span class="sxs-lookup"><span data-stu-id="34497-277">Assign to: Donna</span></span>           |
    | <span data-ttu-id="34497-278">2</span><span class="sxs-lookup"><span data-stu-id="34497-278">2</span></span>        | <span data-ttu-id="34497-279">Przypisać do: Ireny</span><span class="sxs-lookup"><span data-stu-id="34497-279">Assign to: Erin</span></span>            |
    | <span data-ttu-id="34497-280">3</span><span class="sxs-lookup"><span data-stu-id="34497-280">3</span></span>        | <span data-ttu-id="34497-281">Działanie końcowe: \[Wybór 1\]</span><span class="sxs-lookup"><span data-stu-id="34497-281">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="34497-282">W tym przykładzie system przypisuje zaległą decyzję do Danuty.</span><span class="sxs-lookup"><span data-stu-id="34497-282">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="34497-283">Jeśli Danuta nie podejmie decyzji w przydzielonym czasie, system przypisze decyzję do Ireny.</span><span class="sxs-lookup"><span data-stu-id="34497-283">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="34497-284">Jeśli Irena nie podejmie decyzji w przydzielonym czasie, system wybierze opcję **\[Wybór 1\]** jako decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-284">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="34497-285">Aby dodać użytkownika do ścieżki eskalacji, kliknij opcję **Dodaj eskalację**.</span><span class="sxs-lookup"><span data-stu-id="34497-285">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="34497-286">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 4.</span><span class="sxs-lookup"><span data-stu-id="34497-286">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="34497-287">Opcja</span><span class="sxs-lookup"><span data-stu-id="34497-287">Option</span></span></th>
    <th><span data-ttu-id="34497-288">Użytkownicy, do których decyzja jest eskalowana</span><span class="sxs-lookup"><span data-stu-id="34497-288">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="34497-289">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="34497-289">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="34497-290">Hierarchia</span><span class="sxs-lookup"><span data-stu-id="34497-290">Hierarchy</span></span></td>
    <td><span data-ttu-id="34497-291">Użytkownicy w określonej hierarchii organizacyjnej</span><span class="sxs-lookup"><span data-stu-id="34497-291">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-292">Gdy wybierzesz wartość w polu <strong>Hierarchia</strong>, na karcie <strong>Wybór hierarchii</strong> na liście <strong>Typ hierarchii</strong> wybierz typ hierarchii, do której ma zostać eskalowana decyzja.</span><span class="sxs-lookup"><span data-stu-id="34497-292">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="34497-293">System musi pobrać zakres nazwisk użytkowników z hierarchii.</span><span class="sxs-lookup"><span data-stu-id="34497-293">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="34497-294">Te nazwy reprezentują użytkowników, do których można eskalować decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-294">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="34497-295">Wykonaj poniższe kroki, aby określić początek i koniec zakresu nazw użytkowników pobieranych przez system:</span><span class="sxs-lookup"><span data-stu-id="34497-295">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="34497-296">Aby określić początek zakresu, zaznacz osobę na liście <strong>Rozpocznij od</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-296">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="34497-297">Aby określić koniec zakresu, kliknij opcję <strong>Dodaj warunek</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-297">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="34497-298">Następnie wprowadź warunek określający miejsce w hierarchii, w którym system ma zakończyć pobieranie nazwisk.</span><span class="sxs-lookup"><span data-stu-id="34497-298">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="34497-299">Na karcie <strong>Opcje hierarchii</strong> określ, do których użytkowników w zakresie należy eskalować decyzję:</span><span class="sxs-lookup"><span data-stu-id="34497-299">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="34497-300"><strong>Przypisz do wszystkich pobranych użytkowników</strong> — decyzja zostanie eskalowana do wszystkich użytkowników w zakresie.</span><span class="sxs-lookup"><span data-stu-id="34497-300"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="34497-301"><strong>Przypisz tylko do ostatnio pobranego użytkownika</strong> — decyzja zostanie eskalowana tylko do ostatniego użytkownika w zakresie.</span><span class="sxs-lookup"><span data-stu-id="34497-301"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="34497-302"><strong>Nie uwzględniaj użytkowników spełniających następujący warunek:</strong> — decyzja nie będzie eskalowana do żadnych użytkowników w zakresie, którzy spełniają określony warunek.</span><span class="sxs-lookup"><span data-stu-id="34497-302"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="34497-303">Kliknij przycisk <strong>Dodaj warunek</strong>, aby określić warunek.</span><span class="sxs-lookup"><span data-stu-id="34497-303">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-304">Użytkownik przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="34497-304">Workflow user</span></span></td>
    <td><span data-ttu-id="34497-305">Użytkownicy w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="34497-305">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="34497-306">Po wybraniu wartości w polu <strong>Użytkownik przepływu pracy</strong> przejdź do karty <strong>Użytkownik przepływu pracy</strong> i na liście <strong>Użytkownik przepływu pracy</strong> wybierz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="34497-306">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="34497-307">Użytkownik</span><span class="sxs-lookup"><span data-stu-id="34497-307">User</span></span></td>
    <td><span data-ttu-id="34497-308">Konkretny użytkownik programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="34497-308">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="34497-309">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-309">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="34497-310">Lista <strong>Dostępni użytkownicy:</strong> zawiera wszystkich użytkowników programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="34497-310">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="34497-311">Wybierz użytkowników, do których chcesz eskalować decyzję, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="34497-311">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="34497-312">Na karcie **Limit czasu** w polu **Czas trwania** określ czas, jaki użytkownik ma na podjęcie decyzji.</span><span class="sxs-lookup"><span data-stu-id="34497-312">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="34497-313">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="34497-313">Select one of the following options:</span></span>

    - <span data-ttu-id="34497-314">**Godziny** — Wprowadź liczbę godzin, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-314">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="34497-315">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="34497-315">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="34497-316">**Dni** — Wprowadź liczbę dni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-316">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="34497-317">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="34497-317">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="34497-318">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-318">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="34497-319">**Miesiące** — Wybierz dzień i tydzień, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-319">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="34497-320">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="34497-320">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="34497-321">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy użytkownik musi podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-321">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="34497-322">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="34497-322">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="34497-323">Powtórz kroki od 3 do 4 dla każdego użytkownika, który powinien zostać dodany do ścieżki eskalacji.</span><span class="sxs-lookup"><span data-stu-id="34497-323">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="34497-324">Można zmienić kolejność użytkowników.</span><span class="sxs-lookup"><span data-stu-id="34497-324">You can change the order of the users.</span></span>
6. <span data-ttu-id="34497-325">Jeśli użytkownicy wymienieni w ścieżce eskalacji nie podejmą decyzji w wyznaczonym czasie, system sam podejmie decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-325">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="34497-326">Aby określić opcję wybieraną przez system, wybierz wiersz **Akcja**, a następnie na karcie **Zakończ działanie** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="34497-326">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="34497-327">Ustawianie limitu czasu</span><span class="sxs-lookup"><span data-stu-id="34497-327">Set a time limit</span></span>

<span data-ttu-id="34497-328">Jeśli decyzja musi zostać podjęta w określonym czasie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="34497-328">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="34497-329">Opcje wybranej w tej procedurze zastępują opcje wybrane na stronie w obszarach **Przypisanie** i **Eskalacja**.</span><span class="sxs-lookup"><span data-stu-id="34497-329">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="34497-330">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="34497-330">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="34497-331">Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="34497-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="34497-332">W polu **Czas trwania** określ, do kiedy decyzja musi zostać podjęta.</span><span class="sxs-lookup"><span data-stu-id="34497-332">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="34497-333">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="34497-333">Select one of the following options:</span></span>

    - <span data-ttu-id="34497-334">**Godziny** — Wprowadź liczbę godzin.</span><span class="sxs-lookup"><span data-stu-id="34497-334">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="34497-335">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="34497-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="34497-336">**Dni** — Wprowadź liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="34497-336">**Days** – Enter the number of days.</span></span> <span data-ttu-id="34497-337">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="34497-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="34497-338">**Tygodnie** — Wprowadź liczbę tygodni.</span><span class="sxs-lookup"><span data-stu-id="34497-338">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="34497-339">**Miesiące** — Wybierz dzień i tydzień, do kiedy należy podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-339">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="34497-340">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="34497-340">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="34497-341">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy podjąć decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-341">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="34497-342">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="34497-342">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="34497-343">W przypadku przekroczenia tego limitu czasu system sam podejmie decyzję.</span><span class="sxs-lookup"><span data-stu-id="34497-343">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="34497-344">Na liście **Akcja** zaznacz opcję, którą system powinien wybrać.</span><span class="sxs-lookup"><span data-stu-id="34497-344">In the **Action** list, select the option that the system should select.</span></span>
