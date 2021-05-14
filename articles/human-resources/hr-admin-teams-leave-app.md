---
title: Aplikacja Human Resources w Teams
description: W tym temacie przedstawiono aplikację Microsoft Dynamics 365 Human Resources w Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9cc15c33c7efdd515121db67331477baa4bdacaf
ms.sourcegitcommit: e3f11fc9a9dae416a490437678bb482a0094f9a9
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2021
ms.locfileid: "5953395"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="d1a2b-103">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-103">Human Resources app in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d1a2b-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="d1a2b-105">Aby zażądać informacji, pracownicy mogą współpracować z botem.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="d1a2b-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="d1a2b-107">Ponadto mogą wysyłać osobom informacje o zbliżającym się czasie wolnym w zespołach i czatach poza aplikacją Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Karta z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="d1a2b-111">Instalowanie i konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="d1a2b-111">Install and setup</span></span>

<span data-ttu-id="d1a2b-112">Aplikację Dynamics 365 Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-112">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span> <span data-ttu-id="d1a2b-113">Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="d1a2b-114">Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

<span data-ttu-id="d1a2b-115">Jeśli chcesz, aby użytkownicy wyświetlali kalendarz urlopów i nieobecności w aplikacji, musisz włączyć **Kalendarz urlopów i nieobecności w Teams** w zarządzaniu funkcjami w zespołach.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-115">If you want your users to view the Leave and absence calendar in the app, you'll need to enable the **Leave and absence calendar in Teams** in Feature management.</span></span> <span data-ttu-id="d1a2b-116">Aby uzyskać więcej informacji na temat włączania funkcji, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-116">For more information about enabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="d1a2b-117">Włączanie powiadomień dla aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-117">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="d1a2b-118">Jeśli chcesz, aby użytkownicy otrzymywali powiadomienia o żądaniu urlopu w aplikacji Teams, musisz włączyć powiadomienia w module Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-118">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Dynamics 365 Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="d1a2b-119">Tylko użytkownicy zalogowani do zespołów i korzystający z aplikacji Dynamics 365 Human Resources w Teams będą otrzymywali powiadomienia.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-119">Only users who are signed into Teams and using the Dynamics 365 Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="d1a2b-120">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-120">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="d1a2b-121">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-121">Select **Links**.</span></span>

3. <span data-ttu-id="d1a2b-122">W obszarze **Konfiguracja** wybierz opcję **Parametry systemowe**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-122">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="d1a2b-123">Na karcie **Ogólne** określ ustawienie **Włącz powiadomienia dla aplikacji Teams** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-123">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Włącz powiadomienia aplikacji Teams w parametrach systemowych](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="d1a2b-125">Aby włączyć powiadomienia Teams dla wszystkich użytkowników, wybierz **Tak**, gdy wystąpi monit.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-125">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Włącz powiadomienia Teams dla wszystkich użytkowników](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="d1a2b-127">Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników</span><span class="sxs-lookup"><span data-stu-id="d1a2b-127">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="d1a2b-128">Po włączeniu powiadomień dla aplikacji Dynamics 365 Human Resources w Teams, można włączać lub wyłączać powiadomienia dla poszczególnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-128">After you've enabled notifications for the Dynamics 365 Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="d1a2b-129">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="d1a2b-130">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-130">Select **Links**.</span></span>

3. <span data-ttu-id="d1a2b-131">W obszarze **Użytkownicy** wybierz **Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-131">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="d1a2b-132">Wybierz kartę **Przepływ pracy**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-132">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="d1a2b-133">W polu **Włącz powiadomienia dla aplikacji Teams** wybierz wartość **Tak**, aby włączyć powiadomienia dla użytkownika lub **Nie**, aby je wyłączyć.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-133">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Włącz powiadomienia aplikacji Teams na karcie przepływ pracy w opcjach użytkownika](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="d1a2b-135">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-135">Select **Save**.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="d1a2b-136">Obsługiwane języki</span><span class="sxs-lookup"><span data-stu-id="d1a2b-136">Supported languages</span></span>

<span data-ttu-id="d1a2b-137">Aplikacja Dynamics 365 Human Resources w Teams obsługuje następujące języki:</span><span class="sxs-lookup"><span data-stu-id="d1a2b-137">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="d1a2b-138">Identyfikator lokalizacji</span><span class="sxs-lookup"><span data-stu-id="d1a2b-138">Locale ID</span></span> | <span data-ttu-id="d1a2b-139">Język</span><span class="sxs-lookup"><span data-stu-id="d1a2b-139">Language</span></span> |
| --- | --- |
| <span data-ttu-id="d1a2b-140">de-DE</span><span class="sxs-lookup"><span data-stu-id="d1a2b-140">de-DE</span></span> | <span data-ttu-id="d1a2b-141">Niemiecki (Niemcy)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-141">German (Germany)</span></span> |
| <span data-ttu-id="d1a2b-142">es-ES</span><span class="sxs-lookup"><span data-stu-id="d1a2b-142">es-ES</span></span> | <span data-ttu-id="d1a2b-143">Hiszpański (Hiszpania)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-143">Spanish (Spain)</span></span> |
| <span data-ttu-id="d1a2b-144">es-MX</span><span class="sxs-lookup"><span data-stu-id="d1a2b-144">es-MX</span></span> | <span data-ttu-id="d1a2b-145">hiszpański (Meksyk)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-145">Spanish (Mexico)</span></span> |
| <span data-ttu-id="d1a2b-146">fr-CA</span><span class="sxs-lookup"><span data-stu-id="d1a2b-146">fr-CA</span></span> | <span data-ttu-id="d1a2b-147">francuski (Kanada)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-147">French (Canada)</span></span> |
| <span data-ttu-id="d1a2b-148">fr-FR</span><span class="sxs-lookup"><span data-stu-id="d1a2b-148">fr-FR</span></span> | <span data-ttu-id="d1a2b-149">Francuski (Francja)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-149">French (France)</span></span> |
| <span data-ttu-id="d1a2b-150">it-IT</span><span class="sxs-lookup"><span data-stu-id="d1a2b-150">it-IT</span></span> | <span data-ttu-id="d1a2b-151">Włoski (Włochy)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-151">Italian (Italy)</span></span> |
| <span data-ttu-id="d1a2b-152">nl-NL</span><span class="sxs-lookup"><span data-stu-id="d1a2b-152">nl-NL</span></span> | <span data-ttu-id="d1a2b-153">Holenderski (Holandia)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-153">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="d1a2b-154">pt-BR</span><span class="sxs-lookup"><span data-stu-id="d1a2b-154">pt-BR</span></span> | <span data-ttu-id="d1a2b-155">Portugalski (Brazylia)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-155">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="d1a2b-156">tr-TR</span><span class="sxs-lookup"><span data-stu-id="d1a2b-156">tr-TR</span></span> | <span data-ttu-id="d1a2b-157">Turecki (Turcja)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-157">Turkish (Turkey)</span></span> |
| <span data-ttu-id="d1a2b-158">zh-CN</span><span class="sxs-lookup"><span data-stu-id="d1a2b-158">zh-CN</span></span> | <span data-ttu-id="d1a2b-159">Chiński (Uproszczony)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-159">Chinese (Simplified)</span></span> |

## <a name="notes"></a><span data-ttu-id="d1a2b-160">Notatki</span><span class="sxs-lookup"><span data-stu-id="d1a2b-160">Notes</span></span>

<span data-ttu-id="d1a2b-161">Następujące elementy pracy są projektowane w przyszłych wersjach:</span><span class="sxs-lookup"><span data-stu-id="d1a2b-161">The following work items are slated for future releases:</span></span>

| <span data-ttu-id="d1a2b-162">Element pracy</span><span class="sxs-lookup"><span data-stu-id="d1a2b-162">Work item</span></span> | <span data-ttu-id="d1a2b-163">Stan</span><span class="sxs-lookup"><span data-stu-id="d1a2b-163">Status</span></span> |
| --- | --- |
| <span data-ttu-id="d1a2b-164">Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-164">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="d1a2b-165">Prognozowanie nie jest jeszcze dostępne.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-165">Forecasting isn't yet available.</span></span> <span data-ttu-id="d1a2b-166">Jest wyświetlane saldo dla bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-166">The balance displays for the current date.</span></span> |
| <span data-ttu-id="d1a2b-167">Nie można anulować żądań typu **Trwa przegląd**.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-167">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="d1a2b-168">Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-168">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="d1a2b-169">Informacje o saldzie są obliczane na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-169">Balance information is calculated as of today.</span></span> | <span data-ttu-id="d1a2b-170">Obecnie system nie wyświetla sald dla okresu naliczania, nawet jeśli zostało to skonfigurowane w parametrach urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-170">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="d1a2b-171">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="d1a2b-171">Troubleshooting</span></span>

<span data-ttu-id="d1a2b-172">Jeśli użytkownik ma problemy z zalogowaniem się lub użyciem aplikacji Zespoły kadrowe, spróbuj wykonać poniższe instrukcje rozwiązywania problemów.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-172">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="d1a2b-173">Jeśli nadal masz problemy po diagnostyce, skontaktuj się z pomocą techniczną.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-173">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="d1a2b-174">Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-174">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="d1a2b-175">Nie można zalogować się do aplikacji do aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-175">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="d1a2b-176">Jeśli użytkownik kontaktuje się z Tobą, ponieważ nie może zalogować się do aplikacji, należy sprawdzić, czy mają skojarzony rekord pracownika etatowego w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-176">If a user contacts you because they can't sign into the app, verify that they have an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="d1a2b-177">Błąd podczas zatwierdzania żądań urlopu w aplikacji Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-177">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="d1a2b-178">Jeśli użytkownik otrzyma komunikat o błędzie podczas próby zatwierdzenia żądań opuszczenia w aplikacji Teams, należy wypróbować następujące kroki rozwiązywania problemów:</span><span class="sxs-lookup"><span data-stu-id="d1a2b-178">If a user receives an error while trying to approve,  leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="d1a2b-179">Sprawdź, czy ich konta programu Teams są takie same, które służą do uzyskiwania dostępu do modułu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-179">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="d1a2b-180">Sprawdź, czy jest to prawidłowa osoba zatwierdzająca żądanie, sprawdzając ustawienia przepływu pracy do zatwierdzenia urlopu.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-180">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="d1a2b-181">Aby uzyskać więcej informacji o przepływach pracy wniosków o urlop, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-181">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a><span data-ttu-id="d1a2b-182">Osoby zatwierdzające urlopy nie otrzymują komunikatów rozmowy Teams, aby zatwierdzać wnioski urlopowe</span><span class="sxs-lookup"><span data-stu-id="d1a2b-182">Leave approvers don't receive Teams chat messages to approve leave requests</span></span>

1. <span data-ttu-id="d1a2b-183">Upewnij się, że powiadomienia są włączone dla środowiska i użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-183">Ensure notifications are enabled for the environment and the user.</span></span> <span data-ttu-id="d1a2b-184">Więcej informacji znajdziesz w tematach [Włączanie powiadomień dla aplikacji Human Resources w Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) i [Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-184">For more information, see [Enable notifications for the Human Resources app in Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) and [Turn Teams notifications on or off for individual users](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span></span>

2. <span data-ttu-id="d1a2b-185">Upewnij się, że użytkownicy są zalogowani na karcie **Rozmowy** z użyciem tych samych poświadczeń, których używają do zatwierdzania wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-185">Ensure users are signed into the **Chats** tab with the same credentials they use for approving leave requests.</span></span> <span data-ttu-id="d1a2b-186">Użyj komunikatów „wyloguj się”, a następnie „zaloguj się”, aby zalogować się przy użyciu odpowiednich poświadczeń.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-186">Use the messages "sign out" and then "sign in" to sign in with the correct credentials.</span></span>

3. <span data-ttu-id="d1a2b-187">Jeśli problem będzie nadal występował, sprawdź stan zadania wsadowego Zdarzenia biznesowe jako administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-187">If the issue persists, check the status of the Business Events system batch job as a system administrator.</span></span> <span data-ttu-id="d1a2b-188">Jeśli ten etap jest w stanie oczekiwania lub wykonywania, sprawdź ponownie za kilka minut.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-188">If it's in a waiting or executing stage, check back in a few minutes.</span></span> <span data-ttu-id="d1a2b-189">Jeśli ten stan pozostanie niezmieniony, zarejestruj bilet pomocy technicznej, aby nasz zespół był w stanie pomóc w rozwiązaniu problemu.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-189">If the status remains unchanged, log a support ticket so our team can help resolve the issue.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="d1a2b-190">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="d1a2b-190">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="d1a2b-191">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="d1a2b-191">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="d1a2b-192">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-192">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="d1a2b-193">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-193">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="d1a2b-194">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-194">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="d1a2b-195">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-195">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="d1a2b-196">Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-196">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span>

<span data-ttu-id="d1a2b-197">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-197">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="d1a2b-198">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-198">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d1a2b-199">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-199">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="d1a2b-200">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-200">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="d1a2b-201">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-201">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="d1a2b-202">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-202">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="d1a2b-203">Microsoft Teams, Azure Event Grid i Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="d1a2b-203">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="d1a2b-204">Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-204">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="d1a2b-205">Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-205">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="d1a2b-206">Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-206">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="d1a2b-207">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-207">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="d1a2b-208">W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-208">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="d1a2b-209">Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług.</span><span class="sxs-lookup"><span data-stu-id="d1a2b-209">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="d1a2b-210">Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-210">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="d1a2b-211">Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="d1a2b-211">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="d1a2b-212">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="d1a2b-212">See also</span></span> 

[<span data-ttu-id="d1a2b-213">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-213">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="d1a2b-214">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-214">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="d1a2b-215">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="d1a2b-215">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]