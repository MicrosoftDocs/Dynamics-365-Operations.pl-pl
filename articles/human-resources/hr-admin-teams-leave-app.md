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
ms.openlocfilehash: 33322b9b553076125695f257b201463e9d8275c6
ms.sourcegitcommit: e27510ba52623c801353eed4853f8c0aeea3bb2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "3828921"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="8f1f6-103">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="8f1f6-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="8f1f6-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="8f1f6-105">Aby zażądać informacji, pracownicy mogą współpracować z botem.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="8f1f6-106">Zakładka **Czas wolny** zawiera bardziej szczegółowe informacje, a ponadto mogą wysyłać osobom informacje o zbliżającym się czasie wolnym w zespołach i czatach poza aplikacją Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-106">The **Time off** tab provides more detailed information.In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-admin-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Karta z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="8f1f6-110">Instalowanie i konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="8f1f6-110">Install and setup</span></span>

<span data-ttu-id="8f1f6-111">Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-111">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="8f1f6-112">Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-112">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="8f1f6-113">Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-113">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="8f1f6-114">Włączanie powiadomień dla aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="8f1f6-114">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="8f1f6-115">Jeśli chcesz, aby użytkownicy otrzymywali powiadomienia o żądaniu urlopu w aplikacji Teams, musisz włączyć powiadomienia w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-115">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="8f1f6-116">Tylko użytkownicy zalogowani do zespołów i korzystający z aplikacji Human Resources w Teams będą otrzymywali powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-116">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="8f1f6-117">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-117">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="8f1f6-118">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-118">Select **Links**.</span></span>

3. <span data-ttu-id="8f1f6-119">W obszarze **Konfiguracja** wybierz opcję **Parametry systemowe**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-119">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="8f1f6-120">Na karcie **Ogólne** określ ustawienie **Włącz powiadomienia dla aplikacji Teams** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-120">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Włącz powiadomienia aplikacji Teams w parametrach systemowych](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="8f1f6-122">Aby włączyć powiadomienia Teams dla wszystkich użytkowników, wybierz **Tak**, gdy wystąpi monit.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-122">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Włącz powiadomienia Teams dla wszystkich użytkowników](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="8f1f6-124">Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników</span><span class="sxs-lookup"><span data-stu-id="8f1f6-124">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="8f1f6-125">Po włączeniu powiadomień dla aplikacji Human Resources w Teams, można włączać lub wyłączać powiadomienia dla poszczególnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-125">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="8f1f6-126">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="8f1f6-127">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-127">Select **Links**.</span></span>

3. <span data-ttu-id="8f1f6-128">W obszarze **Użytkownicy** wybierz **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-128">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="8f1f6-129">Wybierz kartę **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-129">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="8f1f6-130">W polu **Włącz powiadomienia dla aplikacji Teams** wybierz wartość **Tak**, aby włączyć powiadomienia dla użytkownika lub **Nie**, aby je wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-130">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Włącz powiadomienia aplikacji Teams na karcie przepływ pracy w opcjach użytkownika](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="8f1f6-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-132">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8f1f6-133">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="8f1f6-133">Known issues</span></span>

| <span data-ttu-id="8f1f6-134">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="8f1f6-134">Issue</span></span> | <span data-ttu-id="8f1f6-135">Stan</span><span class="sxs-lookup"><span data-stu-id="8f1f6-135">Status</span></span> |
| --- | --- |
| <span data-ttu-id="8f1f6-136">Przewijanie w poziomie nie działa na telefonach Android</span><span class="sxs-lookup"><span data-stu-id="8f1f6-136">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="8f1f6-137">Przewijanie w poziomie nie jest problemem na urządzeniach z systemem iOS lub komputerach stacjonarnych.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-137">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="8f1f6-138">Pracujemy nad poprawką dla Android.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-138">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="8f1f6-139">Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-139">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="8f1f6-140">Prognozowanie nie jest jeszcze dostępne.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-140">Forecasting isn't yet available.</span></span> <span data-ttu-id="8f1f6-141">Jest wyświetlane saldo dla bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-141">The balance displays for the current date.</span></span> |
| <span data-ttu-id="8f1f6-142">Nie można anulować żądań typu **Trwa przegląd**.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-142">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="8f1f6-143">Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-143">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="8f1f6-144">Informacje o saldzie są obliczane na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-144">Balance information is calculated as of today.</span></span> | <span data-ttu-id="8f1f6-145">Obecnie system nie wyświetla sald dla okresu naliczania, nawet jeśli zostało to skonfigurowane w parametrach urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-145">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="8f1f6-146">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="8f1f6-146">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="8f1f6-147">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="8f1f6-147">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="8f1f6-148">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-148">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="8f1f6-149">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-149">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="8f1f6-150">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-150">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="8f1f6-151">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-151">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="8f1f6-152">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-152">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="8f1f6-153">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-153">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="8f1f6-154">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-154">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="8f1f6-155">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-155">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="8f1f6-156">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-156">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="8f1f6-157">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-157">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="8f1f6-158">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-158">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="8f1f6-159">Microsoft Teams, Azure Event Grid i Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="8f1f6-159">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="8f1f6-160">Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-160">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="8f1f6-161">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-161">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="8f1f6-162">Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-162">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="8f1f6-163">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-163">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="8f1f6-164">W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-164">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="8f1f6-165">Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług.</span><span class="sxs-lookup"><span data-stu-id="8f1f6-165">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="8f1f6-166">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-166">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="8f1f6-167">Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="8f1f6-167">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f1f6-168">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="8f1f6-168">See also</span></span> 

[<span data-ttu-id="8f1f6-169">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f1f6-169">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="8f1f6-170">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8f1f6-170">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="8f1f6-171">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="8f1f6-171">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

