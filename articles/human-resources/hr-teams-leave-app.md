---
title: Zarządzanie wnioskami o urlop w Teams
description: W tym temacie przedstawiono sposób wysyłania wniosku o urlop w aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams.
author: andreabichsel
manager: tfehr
ms.date: 02/23/2021
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
ms.openlocfilehash: 79bded5a241a8d5de1847adff3e663359ce1b26f
ms.sourcegitcommit: d7c18228256daeefbf6518c3ef82fed4f7dbc161
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571735"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="4c78b-103">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4c78b-104">Aplikacja Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c78b-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="4c78b-105">Możesz wejść w interakcję z botem, aby poprosić o informacje i złożyć wniosek o urlop.</span><span class="sxs-lookup"><span data-stu-id="4c78b-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="4c78b-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="4c78b-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="4c78b-107">Możesz też wysyłać użytkownikom informacje o zbliżającym się czasie wolnym w Teams i na czatach poza aplikacją Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4c78b-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="4c78b-108">Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="4c78b-108">Install the app</span></span>

<span data-ttu-id="4c78b-109">Aplikację Dynamics 365 Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="4c78b-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="4c78b-110">W rozwiązaniu Microsoft Teams wybierz symbol wielokropka.</span><span class="sxs-lookup"><span data-stu-id="4c78b-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Symbol wielokropka w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="4c78b-112">Wyszukaj aplikację Dynamics 365 Human Resources, a następnie wybierz kafelek **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Kafelek HR w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="4c78b-114">Wybierz przycisk **Dodaj**, aby zainstalować aplikację.</span><span class="sxs-lookup"><span data-stu-id="4c78b-114">Select the **Add** button to install the app.</span></span>

   ![Instalacji aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="4c78b-116">Jeśli aplikacja nie zaloguje Cię automatycznie, wybierz kartę **Ustawienia**, aby się zalogować.</span><span class="sxs-lookup"><span data-stu-id="4c78b-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Karta Ustawienia w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="4c78b-118">Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.</span><span class="sxs-lookup"><span data-stu-id="4c78b-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="4c78b-119">Jeśli masz dostęp do więcej niż jednego wystąpienia aplikacji Human Resources, możesz wybrać środowisko, z którym chcesz się połączyć, na karcie **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="4c78b-120">Aplikacja obsługuje teraz rolę zabezpieczeń administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="4c78b-121">Korzystanie z bota</span><span class="sxs-lookup"><span data-stu-id="4c78b-121">Use the bot</span></span>

<span data-ttu-id="4c78b-122">Po zainstalowaniu aplikacji zostanie wyświetlony komunikat powitalny informujący o typach akcji, które bot może wykonać w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Komunikat powitalny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="4c78b-124">Podczas pierwszej interakcji z botem być może trzeba będzie się zalogować.</span><span class="sxs-lookup"><span data-stu-id="4c78b-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="4c78b-125">Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.</span><span class="sxs-lookup"><span data-stu-id="4c78b-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="4c78b-126">Możesz poprosić bota o wykonanie następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="4c78b-126">You can ask the bot to:</span></span>

- <span data-ttu-id="4c78b-127">Uruchomienie wniosku o urlop w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-127">Start a leave request for you.</span></span>

  ![Rozpoczynanie rozmowy z wnioskami o urlop w Teams](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="4c78b-129">Bot czatu wypełni dla Ciebie prośbę o urlop.</span><span class="sxs-lookup"><span data-stu-id="4c78b-129">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="4c78b-130">Wybierz opcję **Żądanie czasu wolnego** i edytuj szczegóły swojego żądania.</span><span class="sxs-lookup"><span data-stu-id="4c78b-130">Select **Request time off** and edit the details for your request.</span></span>

  ![Edytuj szczegóły wniosku urlopowego](./media/hr-teams-leave-app-details.png)

- <span data-ttu-id="4c78b-132">Po zakończeniu edytowania szczegółów wniosku urlopowego wybierz opcję **Prześlij**, aby przesłać go do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="4c78b-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Przesyłanie wniosku urlopowego](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="4c78b-134">Zarządzanie urlopami w Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-134">Manage your leave in Teams</span></span>

<span data-ttu-id="4c78b-135">Na karcie **Czas wolny** można wyświetlić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="4c78b-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="4c78b-136">Informacje na temat bilansu dla każdego typu urlopu, w którym Cię zarejestrowano</span><span class="sxs-lookup"><span data-stu-id="4c78b-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="4c78b-137">Nadchodzące wnioski o urlop</span><span class="sxs-lookup"><span data-stu-id="4c78b-137">Upcoming leave requests</span></span>

- <span data-ttu-id="4c78b-138">Wnioski dotyczące czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="4c78b-138">Time-off requests</span></span>

- <span data-ttu-id="4c78b-139">Wnioski o urlopu w wersji roboczej</span><span class="sxs-lookup"><span data-stu-id="4c78b-139">Draft leave requests</span></span>

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="4c78b-141">Tworzenie nowego wniosku</span><span class="sxs-lookup"><span data-stu-id="4c78b-141">Create a new request</span></span>

1. <span data-ttu-id="4c78b-142">Aby utworzyć nowy wniosek o urlop, wybierz pozycję **Nowy wniosek**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-142">To create a new leave request, select **New request**.</span></span>

   ![Nowy wniosek w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="4c78b-144">Wprowadź dzień lub dni, w które chcesz wziąć urlop, a następnie wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-144">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Dodawanie czasu wolnego w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="4c78b-146">Wprowadź kod przyczyny, jeśli ma on zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="4c78b-146">If applicable, enter a reason code.</span></span> <span data-ttu-id="4c78b-147">Wprowadź komentarze i dodaj załączniki.</span><span class="sxs-lookup"><span data-stu-id="4c78b-147">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="4c78b-148">Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="4c78b-148">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="4c78b-149">Możesz również wpisać **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="4c78b-149">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="4c78b-150">Zarządzanie wnioskami w wersji roboczej</span><span class="sxs-lookup"><span data-stu-id="4c78b-150">Manage draft requests</span></span>

1. <span data-ttu-id="4c78b-151">Wybierz kartę **Wersje robocze**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-151">Select the **Drafts** tab.</span></span>

   ![Karta Wersje robocze w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="4c78b-153">Wybierz symbol ołówka, aby edytować wniosek, lub symbol kosza, aby usunąć wniosek.</span><span class="sxs-lookup"><span data-stu-id="4c78b-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="4c78b-154">Wprowadź potrzebne zmiany.</span><span class="sxs-lookup"><span data-stu-id="4c78b-154">Make any necessary changes.</span></span> <span data-ttu-id="4c78b-155">Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="4c78b-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="4c78b-156">Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="4c78b-156">You can also select **Save as draft** to come back to it later.</span></span>

   ![Edytowanie wersji roboczej w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="4c78b-158">Odpowiadanie na powiadomienia Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-158">Respond to Teams notifications</span></span>

<span data-ttu-id="4c78b-159">Gdy użytkownik lub pracownik, dla którego użytkownik jest osobą zatwierdzającą prześle wniosek urlopowy, użytkownik otrzyma powiadomienie w aplikacji Human Resources w Teams.</span><span class="sxs-lookup"><span data-stu-id="4c78b-159">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="4c78b-160">Możesz wybrać powiadomienie, aby je wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="4c78b-160">You can select the notification to view it.</span></span> <span data-ttu-id="4c78b-161">Powiadomienia są również wyświetlane w obszarze **Czatu**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-161">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="4c78b-162">Jeśli jesteś osobą zatwierdzającą, możesz wybrać opcję **Zatwierdzanie** lub **Odmowa** w powiadomieniu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-162">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="4c78b-163">Można również podać opcjonalny komunikat.</span><span class="sxs-lookup"><span data-stu-id="4c78b-163">You can also provide an optional message.</span></span>

![Wnioski o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="4c78b-165">Wysyłanie nadchodzących informacji o czasie do współpracujących</span><span class="sxs-lookup"><span data-stu-id="4c78b-165">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="4c78b-166">Po zainstalowaniu aplikacji Human Resources dla Teams można łatwo wysyłać do współpracowników zespołów lub rozmów informacje o zbliżającym się czasie pracy.</span><span class="sxs-lookup"><span data-stu-id="4c78b-166">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="4c78b-167">W zespole lub rozmowę w Teams wybierz przycisk Human Resources poniżej okna rozmowy.</span><span class="sxs-lookup"><span data-stu-id="4c78b-167">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Przycisk Human Resources poniżej okna rozmowy](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="4c78b-169">Wybierz żądanie opuszczenia, które chcesz udostępnić.</span><span class="sxs-lookup"><span data-stu-id="4c78b-169">Select the leave request you want to share.</span></span> <span data-ttu-id="4c78b-170">Jeśli chcesz udostępnić wersję roboczą wniosku urlopowego, najpierw wybierz opcję **Wersje robocze**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-170">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Wybierz nadchodzące żądanie urlopu do udostępnienia](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="4c78b-172">Twoje żądanie opuszczenia będzie wyświetlane w rozmowie.</span><span class="sxs-lookup"><span data-stu-id="4c78b-172">Your leave request will display in the chat.</span></span>

![Karta z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="4c78b-174">Jeśli udostępniono wersję roboczą żądania, będzie ona wyświetlana jako wersja robocza:</span><span class="sxs-lookup"><span data-stu-id="4c78b-174">If you shared a draft request, it will display as a draft:</span></span>

![Karta wersja robocza z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="4c78b-176">Wyświetlanie kalendarza urlopów zespołu</span><span class="sxs-lookup"><span data-stu-id="4c78b-176">View your team's leave calendar</span></span>

<span data-ttu-id="4c78b-177">Jeśli jesteś menedżerem z bezpośrednimi podwładnymi, możesz wyświetlić zatwierdzony i oczekujący urlop zespołu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-177">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="4c78b-178">W aplikacji zasoby ludzkie w zespołach wybierz opcję **Czas wolny**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-178">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="4c78b-179">Wybierz **Kalendarz zespołu**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-179">Select **Team calendar**.</span></span> <span data-ttu-id="4c78b-180">W kalendarzu są wyświetlane zatwierdzone i oczekujące urlopy bezpośrednich podwładnych.</span><span class="sxs-lookup"><span data-stu-id="4c78b-180">The calendar displays your direct reports' approved and pending time off.</span></span>

   ![Wyświetl kalendarz w aplikacji Human Resources w Teams](./media/hr-teams-leave-app-view-calendar.png)

   > [!NOTE]
   > <span data-ttu-id="4c78b-182">Jeśli nie możesz zobaczyć kalendarza zespołu, poproś administratora o jego włączenie.</span><span class="sxs-lookup"><span data-stu-id="4c78b-182">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="4c78b-183">Aby uzyskać więcej informacji, zobacz temat [Instalowanie i konfigurowanie](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="4c78b-183">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="4c78b-184">Obsługiwane języki</span><span class="sxs-lookup"><span data-stu-id="4c78b-184">Supported languages</span></span>

<span data-ttu-id="4c78b-185">Aplikacja Dynamics 365 Human Resources w Teams obsługuje następujące języki:</span><span class="sxs-lookup"><span data-stu-id="4c78b-185">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="4c78b-186">Identyfikator lokalizacji</span><span class="sxs-lookup"><span data-stu-id="4c78b-186">Locale ID</span></span> | <span data-ttu-id="4c78b-187">Język</span><span class="sxs-lookup"><span data-stu-id="4c78b-187">Language</span></span> |
| --- | --- |
| <span data-ttu-id="4c78b-188">de-DE</span><span class="sxs-lookup"><span data-stu-id="4c78b-188">de-DE</span></span> | <span data-ttu-id="4c78b-189">Niemiecki (Niemcy)</span><span class="sxs-lookup"><span data-stu-id="4c78b-189">German (Germany)</span></span> |
| <span data-ttu-id="4c78b-190">es-ES</span><span class="sxs-lookup"><span data-stu-id="4c78b-190">es-ES</span></span> | <span data-ttu-id="4c78b-191">Hiszpański (Hiszpania)</span><span class="sxs-lookup"><span data-stu-id="4c78b-191">Spanish (Spain)</span></span> |
| <span data-ttu-id="4c78b-192">es-MX</span><span class="sxs-lookup"><span data-stu-id="4c78b-192">es-MX</span></span> | <span data-ttu-id="4c78b-193">hiszpański (Meksyk)</span><span class="sxs-lookup"><span data-stu-id="4c78b-193">Spanish (Mexico)</span></span> |
| <span data-ttu-id="4c78b-194">fr-CA</span><span class="sxs-lookup"><span data-stu-id="4c78b-194">fr-CA</span></span> | <span data-ttu-id="4c78b-195">francuski (Kanada)</span><span class="sxs-lookup"><span data-stu-id="4c78b-195">French (Canada)</span></span> |
| <span data-ttu-id="4c78b-196">fr-FR</span><span class="sxs-lookup"><span data-stu-id="4c78b-196">fr-FR</span></span> | <span data-ttu-id="4c78b-197">Francuski (Francja)</span><span class="sxs-lookup"><span data-stu-id="4c78b-197">French (France)</span></span> |
| <span data-ttu-id="4c78b-198">it-IT</span><span class="sxs-lookup"><span data-stu-id="4c78b-198">it-IT</span></span> | <span data-ttu-id="4c78b-199">Włoski (Włochy)</span><span class="sxs-lookup"><span data-stu-id="4c78b-199">Italian (Italy)</span></span> |
| <span data-ttu-id="4c78b-200">nl-NL</span><span class="sxs-lookup"><span data-stu-id="4c78b-200">nl-NL</span></span> | <span data-ttu-id="4c78b-201">Holenderski (Holandia)</span><span class="sxs-lookup"><span data-stu-id="4c78b-201">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="4c78b-202">pt-BR</span><span class="sxs-lookup"><span data-stu-id="4c78b-202">pt-BR</span></span> | <span data-ttu-id="4c78b-203">Portugalski (Brazylia)</span><span class="sxs-lookup"><span data-stu-id="4c78b-203">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="4c78b-204">tr-TR</span><span class="sxs-lookup"><span data-stu-id="4c78b-204">tr-TR</span></span> | <span data-ttu-id="4c78b-205">Turecki (Turcja)</span><span class="sxs-lookup"><span data-stu-id="4c78b-205">Turkish (Turkey)</span></span> |
| <span data-ttu-id="4c78b-206">zh-CN</span><span class="sxs-lookup"><span data-stu-id="4c78b-206">zh-CN</span></span> | <span data-ttu-id="4c78b-207">Chiński (Uproszczony)</span><span class="sxs-lookup"><span data-stu-id="4c78b-207">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="4c78b-208">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="4c78b-208">Troubleshooting</span></span>

<span data-ttu-id="4c78b-209">Jeśli masz problemy z zalogowaniem się lub użyciem aplikacji Dynamics 365 Human Resources w aplikacji Teams, spróbuj wykonać poniższe instrukcje rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="4c78b-209">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="4c78b-210">Jeśli nadal masz problemy po diagnostyce, skontaktuj się z pomocą techniczną.</span><span class="sxs-lookup"><span data-stu-id="4c78b-210">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="4c78b-211">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="4c78b-211">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="4c78b-212">Nie można zalogować się do aplikacji do aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-212">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="4c78b-213">Jeśli nie możesz zalogować się do aplikacji, być może konto używane do logowania w Microsoft Teams nie jest skojarzone z rekordem pracownika w rozwiązaniu Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4c78b-213">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="4c78b-214">Skontaktuj się z administratorem systemu, aby upewnić się, że rekord pracownika jest poprawnie skojarzony.</span><span class="sxs-lookup"><span data-stu-id="4c78b-214">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="4c78b-215">Tłumaczenia nie są wyświetlane prawidłowo</span><span class="sxs-lookup"><span data-stu-id="4c78b-215">Translations don't display correctly</span></span>

<span data-ttu-id="4c78b-216">Jeśli tłumaczenia nie są wyświetlane zgodnie z oczekiwaniami, upewnij się, że język wybrany w aplikacji Teams jest zgodny z językiem wybranym w **Opcjach użytkownika** zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="4c78b-216">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="4c78b-217">W zespołów sprawdź **Język aplikacji** w **Ustawieniach**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-217">In Teams, look at **App language** in **Settings**.</span></span>

![Ustawienia Teams](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="4c78b-219">W menu Zasoby ludzkie wybierz pozycję **Ustawienia**, a następnie wybierz **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="4c78b-219">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="4c78b-220">Upewnij się, że pole **Język** pasuje do pola **Języka aplikacji** w Teams.</span><span class="sxs-lookup"><span data-stu-id="4c78b-220">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Opcje użytkownika w Zasobach ludzkich](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="4c78b-222">Jeśli nadal wystąpią problemy z tłumaczeniami, poinformuj nas o tym.</span><span class="sxs-lookup"><span data-stu-id="4c78b-222">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="4c78b-223">Aby uzyskać więcej informacji, przejrzyj temat [Uzyskaj pomoc techniczną dla aplikacji Finance and Operations lub usług Lifecycle Services (usługi LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-support?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="4c78b-223">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-support?toc=/dynamics365/human-resources/toc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="4c78b-224">Błąd podczas zatwierdzania żądań urlopu w aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-224">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="4c78b-225">Jeśli otrzymasz komunikat o błędzie podczas próby zatwierdzenia wniosków o urlop w aplikacji Teams, wykonaj następujące kroki, aby rozwiązać problem:</span><span class="sxs-lookup"><span data-stu-id="4c78b-225">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="4c78b-226">Sprawdź, czy konto używane do logowania Microsoft Teams jest takie samo, którego używasz w celu uzyskania dostępu do rozwiązania Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4c78b-226">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="4c78b-227">Sprawdź, czy jesteś prawidłową osobą zatwierdzającą żądanie, sprawdzając ustawienia przepływu pracy do zatwierdzenia urlopu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-227">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="4c78b-228">Aby uzyskać więcej informacji o przepływach pracy wniosków o urlop, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="4c78b-228">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="4c78b-229">Znane problemy dotyczące ułatwień dostępu</span><span class="sxs-lookup"><span data-stu-id="4c78b-229">Known accessibility issues</span></span>

<span data-ttu-id="4c78b-230">W aplikacji Human Resources w Teams pojawiają się następujące problemy ułatwień dostępu (zostaną one naprawione w kolejnych wersjach aplikacji).</span><span class="sxs-lookup"><span data-stu-id="4c78b-230">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="4c78b-231">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="4c78b-231">Issue</span></span> | <span data-ttu-id="4c78b-232">Obejście lub wyjaśnienie problemu</span><span class="sxs-lookup"><span data-stu-id="4c78b-232">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="4c78b-233">Powiększenie do 400% na pulpicie powoduje ukrycie niektórych przycisków akcji.</span><span class="sxs-lookup"><span data-stu-id="4c78b-233">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="4c78b-234">Zaleca się używanie lupy zamiast powiększenia do czasu, aż usuniemy problemy z tym poziomem powiększenia.</span><span class="sxs-lookup"><span data-stu-id="4c78b-234">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="4c78b-235">Na karcie **Czas wolny** funkcja VoiceOver podczas odczytywania nagłówka siatki czasu wolnego informuje o akcji powiązanej z przyciskiem.</span><span class="sxs-lookup"><span data-stu-id="4c78b-235">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="4c78b-236">Nagłówek i elementy siatki są grupowane według lat i można je zwinąć.</span><span class="sxs-lookup"><span data-stu-id="4c78b-236">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="4c78b-237">VoiceOver błędnie interpretuje je jako pozycję, z którą można powiązać działanie.</span><span class="sxs-lookup"><span data-stu-id="4c78b-237">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="4c78b-238">Na karcie **Czas wolny** podczas przechodzenia do **Kodu przyczyny** w nowym wniosku uruchamia się dodatkowy gest przeciągnięcia.</span><span class="sxs-lookup"><span data-stu-id="4c78b-238">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="4c78b-239">Nie ma żadnego ukrytego formantu, do którego można uzyskać dostęp za pomocą tego gestu przeciągnięcia.</span><span class="sxs-lookup"><span data-stu-id="4c78b-239">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="4c78b-240">Przy otwartym kalendarzu przeciągnięcie palcem na karcie **Czas wolny** prowadzi do obszaru poza formantem, zamiast na górę nowego wniosku lub do trybu edycji wniosku.</span><span class="sxs-lookup"><span data-stu-id="4c78b-240">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="4c78b-241">Kiedy dojdziesz do opcji **Przejdź do dzisiaj**, potraktuj tę pozycję jako koniec formantu i przesuń palcem w odwrotnym kierunku, aby wrócić na górę strony.</span><span class="sxs-lookup"><span data-stu-id="4c78b-241">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="4c78b-242">Na karcie **Czatu** podczas wpisywania daty przy użyciu narzędzia wspomagającego lub nawigacji z klawiatury obraz przeskakuje na górę strony.</span><span class="sxs-lookup"><span data-stu-id="4c78b-242">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="4c78b-243">Naciskaj klawisz Tab, aż przejdziesz z powrotem do obszaru wpisywania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="4c78b-243">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="4c78b-244">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="4c78b-244">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="4c78b-245">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="4c78b-245">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="4c78b-246">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="4c78b-246">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="4c78b-247">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="4c78b-247">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="4c78b-248">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="4c78b-248">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="4c78b-249">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="4c78b-249">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="4c78b-250">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4c78b-250">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="4c78b-251">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4c78b-251">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="4c78b-252">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4c78b-252">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="4c78b-253">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="4c78b-253">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="4c78b-254">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="4c78b-254">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="4c78b-255">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="4c78b-255">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="4c78b-256">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="4c78b-256">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="4c78b-257">Microsoft Teams, Azure Event Grid i Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="4c78b-257">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="4c78b-258">Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="4c78b-258">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="4c78b-259">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c78b-259">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="4c78b-260">Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="4c78b-260">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="4c78b-261">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="4c78b-261">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="4c78b-262">W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c78b-262">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="4c78b-263">Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług.</span><span class="sxs-lookup"><span data-stu-id="4c78b-263">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="4c78b-264">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="4c78b-264">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="4c78b-265">Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="4c78b-265">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="4c78b-266">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4c78b-266">See also</span></span>

[<span data-ttu-id="4c78b-267">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-267">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="4c78b-268">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-268">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="4c78b-269">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="4c78b-269">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]