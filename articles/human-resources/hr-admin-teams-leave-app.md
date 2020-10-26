---
title: Aplikacja Human Resources w Teams
description: W tym temacie przedstawiono aplikację Microsoft Dynamics 365 Human Resources w Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
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
ms.openlocfilehash: 51f04e553da822c4e09d31bcd72c71b674ad1f1b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930024"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="9fb57-103">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="9fb57-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9fb57-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="9fb57-105">Aby zażądać informacji, pracownicy mogą współpracować z botem.</span><span class="sxs-lookup"><span data-stu-id="9fb57-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="9fb57-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="9fb57-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="9fb57-107">Ponadto mogą wysyłać osobom informacje o zbliżającym się czasie wolnym w zespołach i czatach poza aplikacją Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9fb57-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-admin-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Karta z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="9fb57-111">Instalowanie i konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="9fb57-111">Install and setup</span></span>

<span data-ttu-id="9fb57-112">Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="9fb57-112">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="9fb57-113">Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="9fb57-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="9fb57-114">Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="9fb57-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="9fb57-115">Włączanie powiadomień dla aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-115">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="9fb57-116">Jeśli chcesz, aby użytkownicy otrzymywali powiadomienia o żądaniu urlopu w aplikacji Teams, musisz włączyć powiadomienia w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9fb57-116">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="9fb57-117">Tylko użytkownicy zalogowani do zespołów i korzystający z aplikacji Human Resources w Teams będą otrzymywali powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="9fb57-117">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="9fb57-118">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-118">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="9fb57-119">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-119">Select **Links**.</span></span>

3. <span data-ttu-id="9fb57-120">W obszarze **Konfiguracja** wybierz opcję **Parametry systemowe**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-120">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="9fb57-121">Na karcie **Ogólne** określ ustawienie **Włącz powiadomienia dla aplikacji Teams** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-121">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Włącz powiadomienia aplikacji Teams w parametrach systemowych](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="9fb57-123">Aby włączyć powiadomienia Teams dla wszystkich użytkowników, wybierz **Tak**, gdy wystąpi monit.</span><span class="sxs-lookup"><span data-stu-id="9fb57-123">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Włącz powiadomienia Teams dla wszystkich użytkowników](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="9fb57-125">Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników</span><span class="sxs-lookup"><span data-stu-id="9fb57-125">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="9fb57-126">Po włączeniu powiadomień dla aplikacji Human Resources w Teams, można włączać lub wyłączać powiadomienia dla poszczególnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="9fb57-126">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="9fb57-127">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="9fb57-128">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-128">Select **Links**.</span></span>

3. <span data-ttu-id="9fb57-129">W obszarze **Użytkownicy** wybierz **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-129">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="9fb57-130">Wybierz kartę **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-130">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="9fb57-131">W polu **Włącz powiadomienia dla aplikacji Teams** wybierz wartość **Tak**, aby włączyć powiadomienia dla użytkownika lub **Nie**, aby je wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="9fb57-131">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Włącz powiadomienia aplikacji Teams na karcie przepływ pracy w opcjach użytkownika](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="9fb57-133">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-133">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9fb57-134">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="9fb57-134">Known issues</span></span>

| <span data-ttu-id="9fb57-135">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="9fb57-135">Issue</span></span> | <span data-ttu-id="9fb57-136">Stan</span><span class="sxs-lookup"><span data-stu-id="9fb57-136">Status</span></span> |
| --- | --- |
| <span data-ttu-id="9fb57-137">Przewijanie w poziomie nie działa na telefonach Android</span><span class="sxs-lookup"><span data-stu-id="9fb57-137">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="9fb57-138">Przewijanie w poziomie nie jest problemem na urządzeniach z systemem iOS lub komputerach stacjonarnych.</span><span class="sxs-lookup"><span data-stu-id="9fb57-138">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="9fb57-139">Pracujemy nad poprawką dla Android.</span><span class="sxs-lookup"><span data-stu-id="9fb57-139">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="9fb57-140">Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="9fb57-140">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="9fb57-141">Prognozowanie nie jest jeszcze dostępne.</span><span class="sxs-lookup"><span data-stu-id="9fb57-141">Forecasting isn't yet available.</span></span> <span data-ttu-id="9fb57-142">Jest wyświetlane saldo dla bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="9fb57-142">The balance displays for the current date.</span></span> |
| <span data-ttu-id="9fb57-143">Nie można anulować żądań typu **Trwa przegląd**.</span><span class="sxs-lookup"><span data-stu-id="9fb57-143">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="9fb57-144">Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="9fb57-144">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="9fb57-145">Informacje o saldzie są obliczane na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="9fb57-145">Balance information is calculated as of today.</span></span> | <span data-ttu-id="9fb57-146">Obecnie system nie wyświetla sald dla okresu naliczania, nawet jeśli zostało to skonfigurowane w parametrach urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="9fb57-146">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="9fb57-147">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="9fb57-147">Troubleshooting</span></span>

<span data-ttu-id="9fb57-148">Jeśli użytkownik ma problemy z zalogowaniem się lub użyciem aplikacji Zespoły kadrowe, spróbuj wykonać poniższe instrukcje rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="9fb57-148">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="9fb57-149">Jeśli nadal masz problemy po diagnostyce, skontaktuj się z pomocą techniczną.</span><span class="sxs-lookup"><span data-stu-id="9fb57-149">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="9fb57-150">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="9fb57-150">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="9fb57-151">Nie można zalogować się do aplikacji do aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-151">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="9fb57-152">Jeśli użytkownik kontaktuje się z Tobą, ponieważ nie może zalogować się do aplikacji, należy sprawdzić, czy użytkownik ma skojarzony rekord pracownika etatowego w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9fb57-152">If a user contacts you because they can't sign into the app, verify that the user has an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="9fb57-153">Błąd podczas zatwierdzania żądań urlopu w aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-153">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="9fb57-154">Jeśli użytkownik otrzyma komunikat o błędzie podczas próby zatwierdzenia żądań opuszczenia w aplikacji Teams, należy wykonać następujące kroki rozwiązywania problemów:</span><span class="sxs-lookup"><span data-stu-id="9fb57-154">If a user receives an error while trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="9fb57-155">Sprawdź, czy ich konta programu Teams są takie same, które służą do uzyskiwania dostępu do modułu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9fb57-155">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="9fb57-156">Sprawdź, czy jest to prawidłowa osoba zatwierdzająca żądanie, sprawdzając ustawienia przepływu pracy do zatwierdzenia urlopu.</span><span class="sxs-lookup"><span data-stu-id="9fb57-156">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="9fb57-157">Aby uzyskać więcej informacji o przepływach pracy wniosków o urlop, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="9fb57-157">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="9fb57-158">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="9fb57-158">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="9fb57-159">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="9fb57-159">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="9fb57-160">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="9fb57-160">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="9fb57-161">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="9fb57-161">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="9fb57-162">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="9fb57-162">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="9fb57-163">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="9fb57-163">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="9fb57-164">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9fb57-164">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="9fb57-165">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9fb57-165">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="9fb57-166">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9fb57-166">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="9fb57-167">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="9fb57-167">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="9fb57-168">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="9fb57-168">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="9fb57-169">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="9fb57-169">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="9fb57-170">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9fb57-170">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="9fb57-171">Microsoft Teams, Azure Event Grid i Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="9fb57-171">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="9fb57-172">Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="9fb57-172">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="9fb57-173">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9fb57-173">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="9fb57-174">Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="9fb57-174">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="9fb57-175">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="9fb57-175">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="9fb57-176">W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9fb57-176">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="9fb57-177">Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług.</span><span class="sxs-lookup"><span data-stu-id="9fb57-177">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="9fb57-178">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="9fb57-178">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="9fb57-179">Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="9fb57-179">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="9fb57-180">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="9fb57-180">See also</span></span> 

[<span data-ttu-id="9fb57-181">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-181">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="9fb57-182">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-182">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="9fb57-183">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="9fb57-183">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

