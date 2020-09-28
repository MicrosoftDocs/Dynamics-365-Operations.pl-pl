---
title: Zarządzanie wnioskami o urlop w Teams
description: W tym temacie przedstawiono sposób wysyłania wniosku o urlop w aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/03/2020
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
ms.openlocfilehash: 0fbf44fe35af3147fd5fb478b6cbfc5a5d0b109d
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766767"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="46d2e-103">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="46d2e-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2e-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="46d2e-105">Aby zażądać informacji, możesz współpracować z botem.</span><span class="sxs-lookup"><span data-stu-id="46d2e-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="46d2e-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="46d2e-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="46d2e-107">Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="46d2e-107">Install the app</span></span>

<span data-ttu-id="46d2e-108">Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2e-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="46d2e-109">W rozwiązaniu Microsoft Teams wybierz symbol wielokropka.</span><span class="sxs-lookup"><span data-stu-id="46d2e-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Symbol wielokropka w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="46d2e-111">Wyszukaj aplikację Dynamics 365 Human Resources, a następnie wybierz kafelek **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Kafelek HR w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="46d2e-113">Wybierz przycisk **Dodaj**, aby zainstalować aplikację.</span><span class="sxs-lookup"><span data-stu-id="46d2e-113">Select the **Add** button to install the app.</span></span>

   ![Instalacji aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="46d2e-115">Jeśli aplikacja nie zaloguje Cię automatycznie, wybierz kartę **Ustawienia**, aby się zalogować.</span><span class="sxs-lookup"><span data-stu-id="46d2e-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Karta Ustawienia w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="46d2e-117">Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.</span><span class="sxs-lookup"><span data-stu-id="46d2e-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="46d2e-118">Jeśli masz dostęp do więcej niż jednego wystąpienia aplikacji Human Resources, możesz wybrać środowisko, z którym chcesz się połączyć, na karcie **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="46d2e-119">Aplikacja nie obsługuje obecnie roli zabezpieczeń Administrator systemu i będzie wyświetlać komunikat o błędzie, jeśli zalogujesz się przy użyciu konta administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="46d2e-120">Aby zalogować się przy użyciu innego konta, na karcie **Ustawienia** wybierz przycisk **Przełącz konta**, a następnie zaloguj się przy użyciu konta użytkownika, które nie ma uprawnień administratora systemu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="46d2e-121">Korzystanie z bota</span><span class="sxs-lookup"><span data-stu-id="46d2e-121">Use the bot</span></span>

<span data-ttu-id="46d2e-122">Po zainstalowaniu aplikacji zostanie wyświetlony komunikat powitalny informujący o typach akcji, które bot może wykonać w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Komunikat powitalny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="46d2e-124">Podczas pierwszej interakcji z botem być może trzeba będzie się zalogować.</span><span class="sxs-lookup"><span data-stu-id="46d2e-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="46d2e-125">Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.</span><span class="sxs-lookup"><span data-stu-id="46d2e-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="46d2e-126">Możesz poprosić bota o wykonanie następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="46d2e-126">You can ask the bot to:</span></span>

- <span data-ttu-id="46d2e-127">Wyświetlenie bilansu nieobecności dla każdego typu urlopu, w którym Cię zarejestrowano.</span><span class="sxs-lookup"><span data-stu-id="46d2e-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Pokazywanie bilansów w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="46d2e-129">Wyświetlenie dodatkowych szczegółów dotyczących określonego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-129">Show additional details about a specific leave type.</span></span>

   ![Pokazywanie szczegółów w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="46d2e-131">Uruchomienie wniosku o urlop w Twoim imieniu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-131">Start a leave request for you.</span></span>

   ![Wysyłanie wniosków o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="46d2e-133">Po rozpoczęciu żądania urlopu można skorygować dni bezpośrednio na karcie.</span><span class="sxs-lookup"><span data-stu-id="46d2e-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Edytowanie wniosku o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="46d2e-135">Po zakończeniu wprowadzania informacji wybierz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="46d2e-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="46d2e-136">Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="46d2e-136">You can also select **Save as draft** to come back to it later.</span></span>

![Przesyłanie wniosku o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="46d2e-138">Zarządzanie urlopami w Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-138">Manage your leave in Teams</span></span>

<span data-ttu-id="46d2e-139">Na karcie **Czas wolny** można wyświetlić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="46d2e-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="46d2e-140">Informacje na temat bilansu dla każdego typu urlopu, w którym Cię zarejestrowano</span><span class="sxs-lookup"><span data-stu-id="46d2e-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="46d2e-141">Nadchodzące wnioski o urlop</span><span class="sxs-lookup"><span data-stu-id="46d2e-141">Upcoming leave requests</span></span>

- <span data-ttu-id="46d2e-142">Wnioski dotyczące czasu wolnego</span><span class="sxs-lookup"><span data-stu-id="46d2e-142">Time-off requests</span></span>

- <span data-ttu-id="46d2e-143">Wnioski o urlopu w wersji roboczej</span><span class="sxs-lookup"><span data-stu-id="46d2e-143">Draft leave requests</span></span>

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="46d2e-145">Tworzenie nowego wniosku</span><span class="sxs-lookup"><span data-stu-id="46d2e-145">Create a new request</span></span>

1. <span data-ttu-id="46d2e-146">Aby utworzyć nowy wniosek o urlop, wybierz pozycję **Nowy wniosek**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-146">To create a new leave request, select **New request**.</span></span>

   ![Nowy wniosek w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="46d2e-148">Wprowadź dzień lub dni, w które chcesz wziąć urlop, a następnie wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Dodawanie czasu wolnego w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="46d2e-150">Wprowadź kod przyczyny, jeśli ma on zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="46d2e-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="46d2e-151">Wprowadź komentarze i dodaj załączniki.</span><span class="sxs-lookup"><span data-stu-id="46d2e-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="46d2e-152">Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="46d2e-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="46d2e-153">Możesz również wpisać **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="46d2e-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="46d2e-154">Zarządzanie wnioskami w wersji roboczej</span><span class="sxs-lookup"><span data-stu-id="46d2e-154">Manage draft requests</span></span>

1. <span data-ttu-id="46d2e-155">Wybierz kartę **Wersje robocze**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-155">Select the **Drafts** tab.</span></span>

   ![Karta Wersje robocze w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="46d2e-157">Wybierz symbol ołówka, aby edytować wniosek, lub symbol kosza, aby usunąć wniosek.</span><span class="sxs-lookup"><span data-stu-id="46d2e-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="46d2e-158">Wprowadź potrzebne zmiany.</span><span class="sxs-lookup"><span data-stu-id="46d2e-158">Make any necessary changes.</span></span> <span data-ttu-id="46d2e-159">Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="46d2e-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="46d2e-160">Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.</span><span class="sxs-lookup"><span data-stu-id="46d2e-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Edytowanie wersji roboczej w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="teams-notifications"></a><span data-ttu-id="46d2e-162">Powiadomienia Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-162">Teams notifications</span></span>

<span data-ttu-id="46d2e-163">Gdy użytkownik lub pracownik, dla którego użytkownik jest osobą zatwierdzającą prześle wniosek urlopowy, użytkownik otrzyma powiadomienie w aplikacji Human Resources w Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2e-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="46d2e-164">Możesz wybrać powiadomienie, aby je wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="46d2e-164">You can select the notification to view it.</span></span> <span data-ttu-id="46d2e-165">Powiadomienia są również wyświetlane w obszarze **Czatu**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="46d2e-166">Jeśli jesteś osobą zatwierdzającą, możesz wybrać opcję **Zatwierdzanie** lub **Odmowa** w powiadomieniu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="46d2e-167">Można również podać opcjonalny komunikat.</span><span class="sxs-lookup"><span data-stu-id="46d2e-167">You can also provide an optional message.</span></span>

![Wnioski o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-notification.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="46d2e-169">Wyświetlanie kalendarza urlopów zespołu</span><span class="sxs-lookup"><span data-stu-id="46d2e-169">View your team's leave calendar</span></span>

<span data-ttu-id="46d2e-170">Jeśli jesteś menedżerem z bezpośrednimi podwładnymi, możesz wyświetlić zatwierdzony i oczekujący urlop zespołu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-170">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="46d2e-171">W aplikacji zasoby ludzkie w zespołach wybierz opcję **Czas wolny**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-171">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="46d2e-172">Wybierz **Kalendarz zespołu**.</span><span class="sxs-lookup"><span data-stu-id="46d2e-172">Select **Team calendar**.</span></span>

   ![Wyświetl kalendarz w aplikacji Human Resources w Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="46d2e-174">W kalendarzu są wyświetlane zatwierdzone i oczekujące urlopy bezpośrednich podwładnych.</span><span class="sxs-lookup"><span data-stu-id="46d2e-174">The calendar displays your direct reports' approved and pending time off.</span></span>

![Kalendarz urlopów w aplikacji Human Resources w Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="privacy-notice"></a><span data-ttu-id="46d2e-176">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="46d2e-176">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="46d2e-177">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="46d2e-177">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="46d2e-178">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="46d2e-178">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="46d2e-179">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="46d2e-179">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="46d2e-180">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="46d2e-180">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="46d2e-181">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="46d2e-181">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="46d2e-182">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="46d2e-182">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="46d2e-183">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="46d2e-183">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="46d2e-184">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="46d2e-184">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="46d2e-185">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="46d2e-185">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="46d2e-186">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="46d2e-186">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="46d2e-187">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="46d2e-187">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="46d2e-188">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="46d2e-188">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="46d2e-189">Siatka zdarzeń Microsoft Azure i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-189">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="46d2e-190">W przypadku korzystania z funkcji powiadomień dla Dynamics 365 Human Resources w Teams, niektóre dane odbiorcy przepływają poza region geograficzny, w którym jest wdrożona usługa Human Resources dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="46d2e-190">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="46d2e-191">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46d2e-191">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="46d2e-192">Dane te mogą być przechowywane przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="46d2e-192">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="46d2e-193">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="46d2e-193">See also</span></span>

[<span data-ttu-id="46d2e-194">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-194">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="46d2e-195">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-195">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="46d2e-196">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="46d2e-196">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
