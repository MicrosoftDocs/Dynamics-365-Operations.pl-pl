---
title: Konfigurowanie procesów zatwierdzania w przepływie pracy
description: Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości procesu zatwierdzania.
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
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4032d5e56b9dd014ec0472abfc1b2ad4a15ff1d
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811388"
---
# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="491c1-103">Konfigurowanie procesów zatwierdzania w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="491c1-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="491c1-104">Procedura zamieszczona poniżej umożliwia skonfigurowanie właściwości procesu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="491c1-105">Aby skonfigurować proces zatwierdzania, w edytorze przepływu pracy kliknij element zatwierdzania prawym przyciskiem myszy i wybierz polecenie **Właściwości**, a zostanie otwarty formularz **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="491c1-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-the-approval-process"></a><span data-ttu-id="491c1-106">Nadawanie nazwy procesowi zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="491c1-106">Name the approval process</span></span>

<span data-ttu-id="491c1-107">Aby wprowadzić nazwę procesu zatwierdzania, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="491c1-107">Follow these steps to enter a name for the approval process.</span></span>

1. <span data-ttu-id="491c1-108">W lewym okienku kliknij przycisk **Ustawienia podstawowe**.</span><span class="sxs-lookup"><span data-stu-id="491c1-108">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="491c1-109">W polu **Nazwa** wprowadź unikatową nazwę procesu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="491c1-110">Określanie, kiedy system automatycznie wykonuje operację na dokumencie</span><span class="sxs-lookup"><span data-stu-id="491c1-110">Specify when the system automatically acts on the document</span></span>

<span data-ttu-id="491c1-111">System można skonfigurować do automatycznego wykonywania operacji na dokumencie, gdy są spełnione określone warunki.</span><span class="sxs-lookup"><span data-stu-id="491c1-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="491c1-112">Na przykład system może zatwierdzać raporty o wydatkach, których suma kwot jest mniejsza niż 100 USD.</span><span class="sxs-lookup"><span data-stu-id="491c1-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="491c1-113">Wykonaj następujące kroki, aby określić, kiedy system podejmuje akcję wobec dokumentu.</span><span class="sxs-lookup"><span data-stu-id="491c1-113">Follow these steps to specify when the system acts on the document.</span></span>

1. <span data-ttu-id="491c1-114">W lewym okienku kliknij opcję **Akcje automatyczne**.</span><span class="sxs-lookup"><span data-stu-id="491c1-114">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="491c1-115">Zaznacz pole wyboru **Włącz akcje automatyczne**.</span><span class="sxs-lookup"><span data-stu-id="491c1-115">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="491c1-116">Kliknij opcję **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="491c1-116">Click **Add condition**.</span></span>
4. <span data-ttu-id="491c1-117">Służy do wprowadzania warunku.</span><span class="sxs-lookup"><span data-stu-id="491c1-117">Enter a condition.</span></span>
5. <span data-ttu-id="491c1-118">W razie potrzeby wprowadź dodatkowe warunki.</span><span class="sxs-lookup"><span data-stu-id="491c1-118">Enter additional conditions, if necessary.</span></span>
6. <span data-ttu-id="491c1-119">Aby sprawdzić, czy wprowadzone warunki są poprawnie skonfigurowane, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="491c1-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="491c1-120">Kliknij opcję **Testuj**, a zostanie otwarty formularz **Warunek testowy przepływu pracy**.</span><span class="sxs-lookup"><span data-stu-id="491c1-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="491c1-121">Wybierz rekord w obszarze **Sprawdź poprawność warunku** formularza.</span><span class="sxs-lookup"><span data-stu-id="491c1-121">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="491c1-122">Kliknij przycisk **Test**.</span><span class="sxs-lookup"><span data-stu-id="491c1-122">Click **Test**.</span></span> <span data-ttu-id="491c1-123">System oszacuje rekord i określi, czy rekord spełnia określone warunki.</span><span class="sxs-lookup"><span data-stu-id="491c1-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="491c1-124">Kliknij przycisk **OK** lub **Anuluj**, aby powrócić do formularza **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="491c1-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7. <span data-ttu-id="491c1-125">Z listy **Akcja automatycznego ukończenia** wybierz akcję, jaką ma podjąć system wobec dokumentu.</span><span class="sxs-lookup"><span data-stu-id="491c1-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="491c1-126">Określanie, kiedy są wysyłane powiadomienia</span><span class="sxs-lookup"><span data-stu-id="491c1-126">Specify when notifications are sent</span></span>

<span data-ttu-id="491c1-127">Możliwe jest wysyłanie do odpowiednich osób powiadomień w przypadku zatwierdzenia, odrzucenia, delegowania lub eskalowania dokumentu albo żądania jego modyfikacji.</span><span class="sxs-lookup"><span data-stu-id="491c1-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="491c1-128">Wykonaj następujące kroki, aby określić, kiedy i do kogo są wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="491c1-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="491c1-129">W lewym okienku kliknij opcję **Powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="491c1-129">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="491c1-130">Zaznacz pola wyboru obok zdarzeń, o których mają być wysyłane powiadomienia:</span><span class="sxs-lookup"><span data-stu-id="491c1-130">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="491c1-131">**Delegowanie** — gdy dokument został przypisany innemu użytkownikowi do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="491c1-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    - <span data-ttu-id="491c1-132">**Eskalowanie** — kiedy przypisany użytkownik nie podjął działań wobec dokumentu w wyznaczonym czasie.</span><span class="sxs-lookup"><span data-stu-id="491c1-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    - <span data-ttu-id="491c1-133">**Zatwierdzanie** — po zatwierdzeniu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="491c1-133">**Approve** – When a document has been approved.</span></span>
    - <span data-ttu-id="491c1-134">**Odrzucanie** — po odrzuceniu dokumentu.</span><span class="sxs-lookup"><span data-stu-id="491c1-134">**Reject** – When a document has been rejected.</span></span>
    - <span data-ttu-id="491c1-135">**Żądanie zmiany** — gdy przypisany użytkownik zażądał wprowadzenia zmiany w przesłanym mu dokumencie.</span><span class="sxs-lookup"><span data-stu-id="491c1-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3. <span data-ttu-id="491c1-136">Zaznacz wiersz zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="491c1-136">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="491c1-137">Kliknij kartę **Tekst powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="491c1-137">Click the **Notification text** tab.</span></span>
5. <span data-ttu-id="491c1-138">W polu tekstowym wprowadź treść powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="491c1-138">In the text box, enter the text for the notification.</span></span>
6. <span data-ttu-id="491c1-139">Aby spersonalizować tekst, można wstawić symbole zastępcze, które będą zastępowane odpowiednimi danymi podczas wyświetlania użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="491c1-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="491c1-140">Aby wstawić symbol zastępczy, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="491c1-140">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="491c1-141">Kliknij pole tekstowe w miejscu, gdzie ma się pojawiać symbol zastępczy.</span><span class="sxs-lookup"><span data-stu-id="491c1-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2. <span data-ttu-id="491c1-142">Kliknij opcję **Wstaw symbol zastępczy**.</span><span class="sxs-lookup"><span data-stu-id="491c1-142">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="491c1-143">Na wyświetlonej liście wybierz symbol zastępczy, który chcesz wstawić.</span><span class="sxs-lookup"><span data-stu-id="491c1-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="491c1-144">Kliknij przycisk **Wstaw**.</span><span class="sxs-lookup"><span data-stu-id="491c1-144">Click **Insert**.</span></span>

7. <span data-ttu-id="491c1-145">Aby dodać tłumaczenia powiadomienia, kliknij opcję **Tłumaczenia**.</span><span class="sxs-lookup"><span data-stu-id="491c1-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="491c1-146">W wyświetlonym formularzu wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="491c1-146">In the form that is displayed, follow these steps:</span></span>

    1. <span data-ttu-id="491c1-147">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="491c1-147">Click **Add**.</span></span>
    2. <span data-ttu-id="491c1-148">Z wyświetlonej listy wybierz język, w którym będziesz wprowadzać tekst.</span><span class="sxs-lookup"><span data-stu-id="491c1-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3. <span data-ttu-id="491c1-149">W polu tekstowym **Przetłumaczony tekst** wprowadź tekst.</span><span class="sxs-lookup"><span data-stu-id="491c1-149">In the **Translated text** text box, enter the text.</span></span>
    4. <span data-ttu-id="491c1-150">Aby spersonalizować tekst, wstaw symbole zastępcze.</span><span class="sxs-lookup"><span data-stu-id="491c1-150">To personalize the text, insert placeholders.</span></span>
    5. <span data-ttu-id="491c1-151">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="491c1-151">Click **Close**.</span></span>

8. <span data-ttu-id="491c1-152">Kliknij kartę **Adresat**.</span><span class="sxs-lookup"><span data-stu-id="491c1-152">Click the **Recipient** tab.</span></span>
9. <span data-ttu-id="491c1-153">Określ, komu zostaną wysłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="491c1-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="491c1-154">Wybierz jedną z opcji w tabeli poniżej, a następnie wykonaj dodatkowe kroki dla tej opcji, zanim przejdziesz do kroku 10.</span><span class="sxs-lookup"><span data-stu-id="491c1-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="491c1-155">Opcja</span><span class="sxs-lookup"><span data-stu-id="491c1-155">Option</span></span></th>
    <th><span data-ttu-id="491c1-156">Adresaci powiadomień</span><span class="sxs-lookup"><span data-stu-id="491c1-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="491c1-157">Dodatkowe kroki</span><span class="sxs-lookup"><span data-stu-id="491c1-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="491c1-158"><strong>Uczestnik</strong></span><span class="sxs-lookup"><span data-stu-id="491c1-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="491c1-159">Użytkownicy, którzy są przypisani do określonej grupy lub roli</span><span class="sxs-lookup"><span data-stu-id="491c1-159">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="491c1-160">Po wybraniu wartości w polu <strong>Uczestnik</strong> kliknij kartę <strong>Oparte na roli</strong>.</span><span class="sxs-lookup"><span data-stu-id="491c1-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="491c1-161">Na liście <strong>Typ uczestnika</strong> wybierz typ grupy lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="491c1-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="491c1-162">Na liście <strong>Uczestnik</strong> wybierz grupę lub rolę, do której mają być wysyłane powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="491c1-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="491c1-163"><strong>Użytkownik przepływu pracy</strong></span><span class="sxs-lookup"><span data-stu-id="491c1-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="491c1-164">Użytkownicy uczestniczący w bieżącym przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="491c1-164">Users who participate in the current workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="491c1-165">Po wybraniu opcji <strong>Użytkownik przepływu pracy</strong> kliknij kartę <strong>Użytkownik przepływu pracy</strong>.</span><span class="sxs-lookup"><span data-stu-id="491c1-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="491c1-166">Na liście <strong>Użytkownik przepływu pracy</strong> zaznacz użytkownika, który uczestniczy w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="491c1-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="491c1-167"><strong>Użytkownik</strong></span><span class="sxs-lookup"><span data-stu-id="491c1-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="491c1-168">Określeni użytkownicy</span><span class="sxs-lookup"><span data-stu-id="491c1-168">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="491c1-169">Po wybraniu wartości w polu <strong>Użytkownik</strong> kliknij kartę <strong>Użytkownik</strong>.</span><span class="sxs-lookup"><span data-stu-id="491c1-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="491c1-170">Wybierz użytkowników, którym chcesz wysyłać powiadomienia, a następnie przenieś tych użytkowników do listy <strong>Wybrani użytkownicy</strong>.</span><span class="sxs-lookup"><span data-stu-id="491c1-170">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="491c1-171">Powtórz kroki od 3 do 9 dla każdego zdarzenia wybranego w kroku 2.</span><span class="sxs-lookup"><span data-stu-id="491c1-171">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="491c1-172"> Określanie ostatecznej osoby zatwierdzającej</span><span class="sxs-lookup"><span data-stu-id="491c1-172">Specify a final approver</span></span>

<span data-ttu-id="491c1-173">Można wyznaczyć osobę ostatecznie zatwierdzającą dla scenariuszy, gdzie osobą zatwierdzającą jest użytkownik, który przesłał dokument do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="491c1-173">You may want to designate a final approver for scenarios where the approver is the person who submitted the document for approval.</span></span> <span data-ttu-id="491c1-174">Aby określić ostateczną osobę zatwierdzającą, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="491c1-174">Follow these steps to specify a final approver.</span></span>

1. <span data-ttu-id="491c1-175">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="491c1-175">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="491c1-176">Zaznacz pole wyboru **Użyj ostatecznej osoby zatwierdzającej**.</span><span class="sxs-lookup"><span data-stu-id="491c1-176">Select the **Use final approver** check box.</span></span>
3. <span data-ttu-id="491c1-177">Wybierz z listy użytkownika, który ma być osobą ostatecznie zatwierdzającą.</span><span class="sxs-lookup"><span data-stu-id="491c1-177">In the list, select the user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="491c1-178">Ustawianie limitu czasu</span><span class="sxs-lookup"><span data-stu-id="491c1-178">Set a time limit</span></span>

<span data-ttu-id="491c1-179">Jeśli proces zatwierdzania musi zostać ukończony w określonym czasie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="491c1-179">Follow these steps if the approval process must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="491c1-180">Opcje wybrane w tych krokach zastąpią opcje wybrane w obszarach **Przypisanie** i **Eskalacja** w poszczególnych krokach zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-180">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span>

1. <span data-ttu-id="491c1-181">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="491c1-181">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="491c1-182">Zaznacz pole wyboru **Ustaw limit czasu dla elementu przepływu** **pracy**.</span><span class="sxs-lookup"><span data-stu-id="491c1-182">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3. <span data-ttu-id="491c1-183">W polu **Czas trwania** określ, do kiedy proces zatwierdzania ma zostać ukończony.</span><span class="sxs-lookup"><span data-stu-id="491c1-183">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="491c1-184">Umożliwia wybranie jednej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="491c1-184">Select one of the following options:</span></span>

    - <span data-ttu-id="491c1-185">**Godziny** — Wprowadź liczbę godzin, w ciągu których należy ukończyć proces zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-185">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="491c1-186">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="491c1-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="491c1-187">**Dni** — Wprowadź liczbę dni, w ciągu których należy ukończyć proces zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-187">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="491c1-188">Następnie wybierz kalendarz używany przez organizację i wprowadź informacje o tygodniu roboczym obowiązującym w organizacji.</span><span class="sxs-lookup"><span data-stu-id="491c1-188">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="491c1-189">**Tygodnie** — Wprowadź liczbę tygodni, w ciągu których należy ukończyć proces zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-189">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    - <span data-ttu-id="491c1-190">**Miesiące** — Wybierz dzień i tydzień, do kiedy należy ukończyć proces zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-190">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="491c1-191">Może to być na przykład piątek trzeciego tygodnia w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="491c1-191">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="491c1-192">**Lata** — Wybierz dzień, tydzień i miesiąc, do kiedy należy ukończyć proces zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-192">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="491c1-193">Może to być na przykład piątek trzeciego tygodnia grudnia.</span><span class="sxs-lookup"><span data-stu-id="491c1-193">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="491c1-194">W przypadku przekroczenia tego limitu czasu system wykona operację na dokumencie.</span><span class="sxs-lookup"><span data-stu-id="491c1-194">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="491c1-195">Na liście **Akcja** zaznacz akcję, jaką ma podjąć system.</span><span class="sxs-lookup"><span data-stu-id="491c1-195">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="491c1-196">Określanie akcji dostępnych użytkownikowi</span><span class="sxs-lookup"><span data-stu-id="491c1-196">Specify which actions are available to the user</span></span>

<span data-ttu-id="491c1-197">Gdy dokument zostanie przypisany do użytkownika, aby go zatwierdził, użytkownik musi zareagować na dokument.</span><span class="sxs-lookup"><span data-stu-id="491c1-197">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="491c1-198">Wykonaj następujące kroki, aby określić, które akcje użytkownik może wykonywać na przesłanym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="491c1-198">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>

1. <span data-ttu-id="491c1-199">W lewym okienku kliknij przycisk **Ustawienia zaawansowane**.</span><span class="sxs-lookup"><span data-stu-id="491c1-199">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="491c1-200">Zaznacz pole wyboru **Zatwierdzanie**, jeśli użytkownik może zatwierdzić dokument.</span><span class="sxs-lookup"><span data-stu-id="491c1-200">Select the **Approve** check box if the user can approve the document.</span></span>
3. <span data-ttu-id="491c1-201">Zaznacz pole wyboru **Odrzucanie**, jeśli użytkownik może odrzucić dokument.</span><span class="sxs-lookup"><span data-stu-id="491c1-201">Select the **Reject** check box the user can reject the document.</span></span>
4. <span data-ttu-id="491c1-202">Zaznacz pole wyboru **Żądanie zmiany**, jeśli użytkownik może wnioskować o zmiany w dokumencie.</span><span class="sxs-lookup"><span data-stu-id="491c1-202">Select the **Request change** check box the user can request changes to the document.</span></span>
5. <span data-ttu-id="491c1-203">Zaznacz pole wyboru **Delegowanie**, jeśli użytkownik może przypisać dokument innemu użytkownikowi do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="491c1-203">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

> [!NOTE]
> <span data-ttu-id="491c1-204">Pole wyboru **Włącz wykonywanie akcji z listy zadań w module Enterprise Portal** zostało wycofane.</span><span class="sxs-lookup"><span data-stu-id="491c1-204">The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="491c1-205"> Konfigurowanie kroków zatwierdzania</span><span class="sxs-lookup"><span data-stu-id="491c1-205">Configure the approval steps</span></span>

<span data-ttu-id="491c1-206">Proces zatwierdzania składa się z kroków zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-206">An approval process consists of approval steps.</span></span> <span data-ttu-id="491c1-207">Należy wykonać poniższą procedurę, aby dodać kroki procesu zatwierdzania i je skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="491c1-207">Complete the following procedure to add steps the approval process and configure the steps.</span></span>

1. <span data-ttu-id="491c1-208">W edytorze przepływu pracy kliknij dwukrotnie procesu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-208">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="491c1-209">Edytor przepływu pracy wyświetli etapy procesu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="491c1-209">The workflow editor displays the steps of the approval process.</span></span>
2. <span data-ttu-id="491c1-210">Aby dodać krok zatwierdzania, przeciągnij go z obszaru **Elementy przepływu pracy** na kanwę.</span><span class="sxs-lookup"><span data-stu-id="491c1-210">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3. <span data-ttu-id="491c1-211">Aby skonfigurować krok zatwierdzania, zobacz [Konfigurowanie kroków zatwierdzania w przepływie pracy](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="491c1-211">To configure an approval step, see [Configure approval steps in a workflow](configure-approval-step-workflow.md).</span></span>
