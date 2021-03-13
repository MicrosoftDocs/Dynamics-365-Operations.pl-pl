---
title: Zarządzanie wnioskami o urlop w Teams
description: W tym temacie przedstawiono sposób wysyłania wniosku o urlop w aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams.
author: andreabichsel
manager: tfehr
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 342106ad09db3a5d9c2dec8ab18e824d70e0f6bf
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128168"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="278c3-103">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="278c3-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="278c3-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="278c3-105">Możesz wejść w interakcję z botem, aby poprosić o informacje i złożyć wniosek o urlop.</span><span class="sxs-lookup"><span data-stu-id="278c3-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="278c3-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="278c3-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="278c3-107">Możesz też wysyłać użytkownikom informacje o zbliżającym się czasie wolnym w zespołach i na czatach poza aplikacją Human Resources.</span><span class="sxs-lookup"><span data-stu-id="278c3-107">You can also send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="278c3-108">Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="278c3-108">Install the app</span></span>

<span data-ttu-id="278c3-109">Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="278c3-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="278c3-110">W rozwiązaniu Microsoft Teams wybierz symbol wielokropka.</span><span class="sxs-lookup"><span data-stu-id="278c3-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Symbol wielokropka w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="278c3-112">Wyszukaj aplikację Dynamics 365 Human Resources, a następnie wybierz kafelek **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="278c3-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Kafelek HR w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="278c3-114">Wybierz przycisk **Dodaj**, aby zainstalować aplikację.</span><span class="sxs-lookup"><span data-stu-id="278c3-114">Select the **Add** button to install the app.</span></span>

   ![Instalacji aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="278c3-116">Jeśli aplikacja nie zaloguje Cię automatycznie, wybierz kartę **Ustawienia**, aby się zalogować.</span><span class="sxs-lookup"><span data-stu-id="278c3-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Karta Ustawienia w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="278c3-118">Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.</span><span class="sxs-lookup"><span data-stu-id="278c3-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="278c3-119">Jeśli masz dostęp do więcej niż jednego wystąpienia aplikacji Human Resources, możesz wybrać środowisko, z którym chcesz się połączyć, na karcie **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="278c3-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="278c3-120">Aplikacja obsługuje teraz rolę zabezpieczeń administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="278c3-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="278c3-121">Korzystanie z bota</span><span class="sxs-lookup"><span data-stu-id="278c3-121">Use the bot</span></span>

<span data-ttu-id="278c3-122">Po zainstalowaniu aplikacji zostanie wyświetlony komunikat powitalny informujący o typach akcji, które bot może wykonać w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="278c3-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Komunikat powitalny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="278c3-124">Podczas pierwszej interakcji z botem być może trzeba będzie się zalogować.</span><span class="sxs-lookup"><span data-stu-id="278c3-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="278c3-125">Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.</span><span class="sxs-lookup"><span data-stu-id="278c3-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="278c3-126">Możesz poprosić bota o wykonanie następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="278c3-126">You can ask the bot to:</span></span>

- <span data-ttu-id="278c3-127">Wyświetlenie bilansu nieobecności dla każdego typu urlopu, w którym Cię zarejestrowano.</span><span class="sxs-lookup"><span data-stu-id="278c3-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Pokazywanie bilansów w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="278c3-129">Wyświetlenie dodatkowych szczegółów dotyczących określonego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="278c3-129">Show additional details about a specific leave type.</span></span>

   ![Pokazywanie szczegółów w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="278c3-131">Uruchomienie wniosku o urlop w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="278c3-131">Start a leave request for you.</span></span>

   ![Wysyłanie wniosków o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="278c3-133">Po rozpoczęciu żądania urlopu można skorygować dni bezpośrednio na karcie.</span><span class="sxs-lookup"><span data-stu-id="278c3-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Edytowanie wniosku o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="278c3-135">Po zakończeniu wprowadzania informacji wybierz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="278c3-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="278c3-136">Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="278c3-136">You can also select **Save as draft** to come back to it later.</span></span>

![Przesyłanie wniosku o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="278c3-138">Zarządzanie urlopami w Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-138">Manage your leave in Teams</span></span>

<span data-ttu-id="278c3-139">Na karcie **Czas wolny** można wyświetlić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="278c3-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="278c3-140">Informacje na temat bilansu dla każdego typu urlopu, w którym Cię zarejestrowano</span><span class="sxs-lookup"><span data-stu-id="278c3-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="278c3-141">Nadchodzące wnioski o urlop</span><span class="sxs-lookup"><span data-stu-id="278c3-141">Upcoming leave requests</span></span>

- <span data-ttu-id="278c3-142">Wnioski dotyczące czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="278c3-142">Time-off requests</span></span>

- <span data-ttu-id="278c3-143">Wnioski o urlopu w wersji roboczej</span><span class="sxs-lookup"><span data-stu-id="278c3-143">Draft leave requests</span></span>

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="278c3-145">Tworzenie nowego wniosku</span><span class="sxs-lookup"><span data-stu-id="278c3-145">Create a new request</span></span>

1. <span data-ttu-id="278c3-146">Aby utworzyć nowy wniosek o urlop, wybierz pozycję **Nowy wniosek**.</span><span class="sxs-lookup"><span data-stu-id="278c3-146">To create a new leave request, select **New request**.</span></span>

   ![Nowy wniosek w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="278c3-148">Wprowadź dzień lub dni, w które chcesz wziąć urlop, a następnie wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="278c3-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Dodawanie czasu wolnego w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="278c3-150">Wprowadź kod przyczyny, jeśli ma on zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="278c3-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="278c3-151">Wprowadź komentarze i dodaj załączniki.</span><span class="sxs-lookup"><span data-stu-id="278c3-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="278c3-152">Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="278c3-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="278c3-153">Możesz również wpisać **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="278c3-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="278c3-154">Zarządzanie wnioskami w wersji roboczej</span><span class="sxs-lookup"><span data-stu-id="278c3-154">Manage draft requests</span></span>

1. <span data-ttu-id="278c3-155">Wybierz kartę **Wersje robocze**.</span><span class="sxs-lookup"><span data-stu-id="278c3-155">Select the **Drafts** tab.</span></span>

   ![Karta Wersje robocze w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="278c3-157">Wybierz symbol ołówka, aby edytować wniosek, lub symbol kosza, aby usunąć wniosek.</span><span class="sxs-lookup"><span data-stu-id="278c3-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="278c3-158">Wprowadź potrzebne zmiany.</span><span class="sxs-lookup"><span data-stu-id="278c3-158">Make any necessary changes.</span></span> <span data-ttu-id="278c3-159">Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="278c3-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="278c3-160">Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="278c3-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Edytowanie wersji roboczej w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="278c3-162">Odpowiadanie na powiadomienia Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-162">Respond to Teams notifications</span></span>

<span data-ttu-id="278c3-163">Gdy użytkownik lub pracownik, dla którego użytkownik jest osobą zatwierdzającą prześle wniosek urlopowy, użytkownik otrzyma powiadomienie w aplikacji Human Resources w Teams.</span><span class="sxs-lookup"><span data-stu-id="278c3-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="278c3-164">Możesz wybrać powiadomienie, aby je wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="278c3-164">You can select the notification to view it.</span></span> <span data-ttu-id="278c3-165">Powiadomienia są również wyświetlane w obszarze **Czatu**.</span><span class="sxs-lookup"><span data-stu-id="278c3-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="278c3-166">Jeśli jesteś osobą zatwierdzającą, możesz wybrać opcję **Zatwierdzanie** lub **Odmowa** w powiadomieniu.</span><span class="sxs-lookup"><span data-stu-id="278c3-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="278c3-167">Można również podać opcjonalny komunikat.</span><span class="sxs-lookup"><span data-stu-id="278c3-167">You can also provide an optional message.</span></span>

![Wnioski o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="278c3-169">Wysyłanie nadchodzących informacji o czasie do współpracujących</span><span class="sxs-lookup"><span data-stu-id="278c3-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="278c3-170">Po zainstalowaniu aplikacji Human Resources dla Teams można łatwo wysyłać do współpracowników zespołów lub rozmów informacje o zbliżającym się czasie pracy.</span><span class="sxs-lookup"><span data-stu-id="278c3-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="278c3-171">W zespole lub rozmowę w Teams wybierz przycisk Human Resources poniżej okna rozmowy.</span><span class="sxs-lookup"><span data-stu-id="278c3-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Przycisk Human Resources poniżej okna rozmowy](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="278c3-173">Wybierz żądanie opuszczenia, które chcesz udostępnić.</span><span class="sxs-lookup"><span data-stu-id="278c3-173">Select the leave request you want to share.</span></span> <span data-ttu-id="278c3-174">Jeśli chcesz udostępnić wersję roboczą wniosku urlopowego, najpierw wybierz opcję **Wersje robocze**.</span><span class="sxs-lookup"><span data-stu-id="278c3-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Wybierz nadchodzące żądanie urlopu do udostępnienia](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="278c3-176">Twoje żądanie opuszczenia będzie wyświetlane w rozmowie.</span><span class="sxs-lookup"><span data-stu-id="278c3-176">Your leave request will display in the chat.</span></span>

![Karta z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="278c3-178">Jeśli udostępniono wersję roboczą żądania, będzie ona wyświetlana jako wersja robocza:</span><span class="sxs-lookup"><span data-stu-id="278c3-178">If you shared a draft request, it will display as a draft:</span></span>

![Karta wersja robocza z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="278c3-180">Wyświetlanie kalendarza urlopów zespołu</span><span class="sxs-lookup"><span data-stu-id="278c3-180">View your team's leave calendar</span></span>

<span data-ttu-id="278c3-181">Jeśli jesteś menedżerem z bezpośrednimi podwładnymi, możesz wyświetlić zatwierdzony i oczekujący urlop zespołu.</span><span class="sxs-lookup"><span data-stu-id="278c3-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="278c3-182">W aplikacji zasoby ludzkie w zespołach wybierz opcję **Czas wolny**.</span><span class="sxs-lookup"><span data-stu-id="278c3-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="278c3-183">Wybierz **Kalendarz zespołu**.</span><span class="sxs-lookup"><span data-stu-id="278c3-183">Select **Team calendar**.</span></span>

   ![Wyświetl kalendarz w aplikacji Human Resources w Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="278c3-185">W kalendarzu są wyświetlane zatwierdzone i oczekujące urlopy bezpośrednich podwładnych.</span><span class="sxs-lookup"><span data-stu-id="278c3-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Kalendarz urlopów w aplikacji Human Resources w Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a><span data-ttu-id="278c3-187">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="278c3-187">Troubleshooting</span></span>

<span data-ttu-id="278c3-188">Jeśli masz problemy z zalogowaniem się lub użyciem aplikacji Human Resources w aplikacji Teams, spróbuj wykonać poniższe instrukcje rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="278c3-188">If you're having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="278c3-189">Jeśli nadal masz problemy po diagnostyce, skontaktuj się z pomocą techniczną.</span><span class="sxs-lookup"><span data-stu-id="278c3-189">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="278c3-190">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="278c3-190">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="278c3-191">Nie można zalogować się do aplikacji do aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-191">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="278c3-192">Jeśli nie możesz zalogować się do aplikacji, być może konto używane do logowania w Microsoft Teams nie jest skojarzone z rekordem pracownika w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="278c3-192">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="278c3-193">Skontaktuj się z administratorem systemu, aby upewnić się, że rekord pracownika jest poprawnie skojarzony.</span><span class="sxs-lookup"><span data-stu-id="278c3-193">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="278c3-194">Błąd podczas zatwierdzania żądań urlopu w aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-194">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="278c3-195">Jeśli otrzymasz komunikat o błędzie podczas próby zatwierdzenia wniosków o urlop w aplikacji Teams, wykonaj następujące kroki, aby rozwiązać problem:</span><span class="sxs-lookup"><span data-stu-id="278c3-195">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="278c3-196">Sprawdź, czy konto używane do logowania Microsoft Teams jest takie samo, którego używasz w celu uzyskania dostępu do rozwiązania Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="278c3-196">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="278c3-197">Sprawdź, czy jesteś prawidłową osobą zatwierdzającą żądanie, sprawdzając ustawienia przepływu pracy do zatwierdzenia urlopu.</span><span class="sxs-lookup"><span data-stu-id="278c3-197">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="278c3-198">Aby uzyskać więcej informacji o przepływach pracy wniosków o urlop, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="278c3-198">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="278c3-199">Znane problemy dotyczące ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="278c3-199">Known accessibility issues</span></span>

<span data-ttu-id="278c3-200">W aplikacji Human Resources w Teams pojawiają się następujące problemy ułatwień dostępu (zostaną one naprawione w kolejnych wersjach aplikacji).</span><span class="sxs-lookup"><span data-stu-id="278c3-200">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="278c3-201">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="278c3-201">Issue</span></span> | <span data-ttu-id="278c3-202">Obejście lub wyjaśnienie problemu</span><span class="sxs-lookup"><span data-stu-id="278c3-202">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="278c3-203">Powiększenie do 400% na pulpicie powoduje ukrycie niektórych przycisków akcji.</span><span class="sxs-lookup"><span data-stu-id="278c3-203">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="278c3-204">Zaleca się używanie lupy zamiast powiększenia do czasu, aż usuniemy problemy z tym poziomem powiększenia.</span><span class="sxs-lookup"><span data-stu-id="278c3-204">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="278c3-205">Na karcie **Czas wolny** funkcja VoiceOver podczas odczytywania nagłówka siatki czasu wolnego informuje o akcji powiązanej z przyciskiem.</span><span class="sxs-lookup"><span data-stu-id="278c3-205">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="278c3-206">Nagłówek i elementy siatki są grupowane według lat i można je zwinąć.</span><span class="sxs-lookup"><span data-stu-id="278c3-206">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="278c3-207">VoiceOver błędnie interpretuje je jako pozycję, z którą można powiązać działanie.</span><span class="sxs-lookup"><span data-stu-id="278c3-207">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="278c3-208">Na karcie **Czas wolny** podczas przechodzenia do **Kodu przyczyny** w nowym wniosku uruchamia się dodatkowy gest przeciągnięcia.</span><span class="sxs-lookup"><span data-stu-id="278c3-208">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="278c3-209">Nie ma żadnego ukrytego formantu, do którego można uzyskać dostęp za pomocą tego gestu przeciągnięcia.</span><span class="sxs-lookup"><span data-stu-id="278c3-209">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="278c3-210">Przy otwartym kalendarzu przeciągnięcie palcem na karcie **Czas wolny** prowadzi do obszaru poza formantem, zamiast na górę nowego wniosku lub do trybu edycji wniosku.</span><span class="sxs-lookup"><span data-stu-id="278c3-210">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="278c3-211">Kiedy dojdziesz do opcji **Przejdź do dzisiaj**, potraktuj tę pozycję jako koniec formantu i przesuń palcem w odwrotnym kierunku, aby wrócić na górę strony.</span><span class="sxs-lookup"><span data-stu-id="278c3-211">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="278c3-212">VoiceOver nie odczytuje etykiet dat.</span><span class="sxs-lookup"><span data-stu-id="278c3-212">Voiceover doesn't read the labels for dates.</span></span> | <span data-ttu-id="278c3-213">Daty, które wyświetlają się w parach, to zawsze **Data rozpoczęcia** i **Data zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="278c3-213">The dates encountered in pairs are always **Start date** and **End date**.</span></span> |
| <span data-ttu-id="278c3-214">Na karcie **Czatu** podczas wpisywania daty przy użyciu narzędzia wspomagającego lub nawigacji z klawiatury obraz przeskakuje na górę strony.</span><span class="sxs-lookup"><span data-stu-id="278c3-214">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="278c3-215">Naciskaj klawisz Tab, aż przejdziesz z powrotem do obszaru wpisywania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="278c3-215">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="278c3-216">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="278c3-216">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="278c3-217">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="278c3-217">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="278c3-218">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="278c3-218">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="278c3-219">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="278c3-219">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="278c3-220">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="278c3-220">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="278c3-221">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="278c3-221">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="278c3-222">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="278c3-222">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="278c3-223">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="278c3-223">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="278c3-224">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="278c3-224">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="278c3-225">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="278c3-225">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="278c3-226">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="278c3-226">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="278c3-227">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="278c3-227">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="278c3-228">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="278c3-228">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="278c3-229">Microsoft Teams, Azure Event Grid i Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="278c3-229">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="278c3-230">Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="278c3-230">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="278c3-231">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="278c3-231">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="278c3-232">Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="278c3-232">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="278c3-233">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="278c3-233">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="278c3-234">W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="278c3-234">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="278c3-235">Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług.</span><span class="sxs-lookup"><span data-stu-id="278c3-235">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="278c3-236">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="278c3-236">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="278c3-237">Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="278c3-237">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="278c3-238">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="278c3-238">See also</span></span>

[<span data-ttu-id="278c3-239">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-239">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="278c3-240">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-240">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="278c3-241">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="278c3-241">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
