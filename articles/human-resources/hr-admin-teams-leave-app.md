---
title: Aplikacja Human Resources w Teams
description: W tym temacie przedstawiono aplikację Microsoft Dynamics 365 Human Resources w Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776315"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="499c2-103">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="499c2-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="499c2-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="499c2-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="499c2-105">Aby zażądać informacji, pracownicy mogą współpracować z botem.</span><span class="sxs-lookup"><span data-stu-id="499c2-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="499c2-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="499c2-106">The **Time off** tab provides more detailed information.</span></span>

![Bot w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-admin-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="499c2-109">Instalowanie i konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="499c2-109">Install and setup</span></span>

<span data-ttu-id="499c2-110">Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="499c2-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="499c2-111">Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="499c2-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="499c2-112">Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="499c2-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="499c2-113">Włączanie powiadomień dla aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="499c2-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="499c2-114">Jeśli chcesz, aby użytkownicy otrzymywali powiadomienia o żądaniu urlopu w aplikacji Teams, musisz włączyć powiadomienia w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="499c2-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="499c2-115">Tylko użytkownicy zalogowani do zespołów i korzystający z aplikacji Human Resources w Teams będą otrzymywali powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="499c2-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="499c2-116">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="499c2-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="499c2-117">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="499c2-117">Select **Links**.</span></span>

3. <span data-ttu-id="499c2-118">W obszarze **Konfiguracja** wybierz opcję **Parametry systemowe**.</span><span class="sxs-lookup"><span data-stu-id="499c2-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="499c2-119">Na karcie **Ogólne** określ ustawienie **Włącz powiadomienia dla aplikacji Teams** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="499c2-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Włącz powiadomienia aplikacji Teams w parametrach systemowych](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="499c2-121">Aby włączyć powiadomienia Teams dla wszystkich użytkowników, wybierz **Tak**, gdy wystąpi monit.</span><span class="sxs-lookup"><span data-stu-id="499c2-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Włącz powiadomienia Teams dla wszystkich użytkowników](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="499c2-123">Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników</span><span class="sxs-lookup"><span data-stu-id="499c2-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="499c2-124">Po włączeniu powiadomień dla aplikacji Human Resources w Teams, można włączać lub wyłączać powiadomienia dla poszczególnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="499c2-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="499c2-125">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="499c2-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="499c2-126">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="499c2-126">Select **Links**.</span></span>

3. <span data-ttu-id="499c2-127">W obszarze **Użytkownicy** wybierz **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="499c2-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="499c2-128">Wybierz kartę **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="499c2-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="499c2-129">W polu **Włącz powiadomienia dla aplikacji Teams** wybierz wartość **Tak**, aby włączyć powiadomienia dla użytkownika lub **Nie**, aby je wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="499c2-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Włącz powiadomienia aplikacji Teams na karcie przepływ pracy w opcjach użytkownika](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="499c2-131">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="499c2-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="499c2-132">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="499c2-132">Known issues</span></span>

| <span data-ttu-id="499c2-133">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="499c2-133">Issue</span></span> | <span data-ttu-id="499c2-134">Stan</span><span class="sxs-lookup"><span data-stu-id="499c2-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="499c2-135">Przewijanie w poziomie nie działa na telefonach Android</span><span class="sxs-lookup"><span data-stu-id="499c2-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="499c2-136">Przewijanie w poziomie nie jest problemem na urządzeniach z systemem iOS lub komputerach stacjonarnych.</span><span class="sxs-lookup"><span data-stu-id="499c2-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="499c2-137">Pracujemy nad poprawką dla Android.</span><span class="sxs-lookup"><span data-stu-id="499c2-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="499c2-138">Błąd: Wystąpił problem ze znalezieniem środowiska, z którym można się połączyć.</span><span class="sxs-lookup"><span data-stu-id="499c2-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="499c2-139">Ten błąd może wystąpić, nawet jeśli zweryfikowano, że użytkownik może uzyskać dostęp do jednego lub więcej środowisk Human Resources.</span><span class="sxs-lookup"><span data-stu-id="499c2-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="499c2-140">Ponadto mogą nie być widoczne wszystkie oczekiwane środowiska.</span><span class="sxs-lookup"><span data-stu-id="499c2-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="499c2-141">Do czasu rozwiązania problemu usuń użytkownika, a następnie zaimportuj go ponownie, aby rozwiązać problem.</span><span class="sxs-lookup"><span data-stu-id="499c2-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="499c2-142">Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="499c2-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="499c2-143">Prognozowanie nie jest jeszcze dostępne.</span><span class="sxs-lookup"><span data-stu-id="499c2-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="499c2-144">Jest wyświetlane saldo dla bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="499c2-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="499c2-145">Nie można anulować żądań typu **Trwa przegląd**.</span><span class="sxs-lookup"><span data-stu-id="499c2-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="499c2-146">Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="499c2-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="499c2-147">Informacje o saldzie są obliczane na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="499c2-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="499c2-148">Obecnie system nie wyświetla sald dla okresu naliczania, nawet jeśli zostało to skonfigurowane w parametrach urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="499c2-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="499c2-149">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="499c2-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="499c2-150">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="499c2-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="499c2-151">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="499c2-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="499c2-152">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="499c2-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="499c2-153">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="499c2-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="499c2-154">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="499c2-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="499c2-155">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="499c2-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="499c2-156">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="499c2-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="499c2-157">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="499c2-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="499c2-158">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="499c2-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="499c2-159">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="499c2-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="499c2-160">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="499c2-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="499c2-161">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="499c2-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="499c2-162">Siatka zdarzeń Microsoft Azure i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="499c2-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="499c2-163">W przypadku korzystania z funkcji powiadomień dla Dynamics 365 Human Resources w Teams, niektóre dane odbiorcy przepływają poza region geograficzny, w którym jest wdrożona usługa Human Resources dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="499c2-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="499c2-164">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="499c2-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="499c2-165">Dane te mogą być przechowywane przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="499c2-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="499c2-166">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="499c2-166">See also</span></span> 

[<span data-ttu-id="499c2-167">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="499c2-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="499c2-168">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="499c2-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="499c2-169">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="499c2-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

