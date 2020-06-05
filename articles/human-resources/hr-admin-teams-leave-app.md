---
title: Aplikacja Human Resources w Teams
description: W tym temacie przedstawiono aplikację Microsoft Dynamics 365 Human Resources w Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 423ec36a73e8af9d915c5cfe16bd4d552448e2b6
ms.sourcegitcommit: d1541831d556b722a71aed442043ffb4a4576d87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2020
ms.locfileid: "3388123"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="2b3ac-103">Aplikacja Human Resources w Teams</span><span class="sxs-lookup"><span data-stu-id="2b3ac-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="2b3ac-104">Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="2b3ac-105">Aby zażądać informacji, pracownicy mogą współpracować z botem.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="2b3ac-106">Karta **Czas wolny** zawiera bardziej szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-106">The **Time off** tab provides more detailed information.</span></span>

![Bot w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-admin-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="2b3ac-109">Instalowanie i konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="2b3ac-109">Install and setup</span></span>

<span data-ttu-id="2b3ac-110">Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="2b3ac-111">Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="2b3ac-112">Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="2b3ac-113">Znane problemy</span><span class="sxs-lookup"><span data-stu-id="2b3ac-113">Known issues</span></span>

| <span data-ttu-id="2b3ac-114">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="2b3ac-114">Issue</span></span> | <span data-ttu-id="2b3ac-115">Stan</span><span class="sxs-lookup"><span data-stu-id="2b3ac-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="2b3ac-116">Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-116">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="2b3ac-117">Prognozowanie nie jest jeszcze dostępne.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-117">Forecasting isn't yet available.</span></span> <span data-ttu-id="2b3ac-118">Jest wyświetlane saldo dla bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-118">The balance displays for the current date.</span></span> |
| <span data-ttu-id="2b3ac-119">W przypadku zmniejszenia liczby godzin w istniejącym żądaniu **Pozostałe saldo** zmniejsza się, a nie zwiększa.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-119">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="2b3ac-120">Ten problem zostanie rozwiązany w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-120">We'll address this known issue in the future.</span></span> <span data-ttu-id="2b3ac-121">Wyświetlone dane są niepoprawne, ale podczas przesyłania ilości są odpowiednio korygowane.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-121">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="2b3ac-122">Dla tych samych dat są wyświetlane dwie karty **nadchodzącego czasu wolnego**.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-122">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="2b3ac-123">Karty reprezentują pojedyncze przesłania.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-123">The cards represent individual submissions.</span></span> <span data-ttu-id="2b3ac-124">Będziemy nadal gromadzić opinie i wprowadzać korekty.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-124">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="2b3ac-125">Nie można anulować żądań typu **Trwa przegląd**.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-125">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="2b3ac-126">Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-126">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="2b3ac-127">Informacje o saldzie są obliczane na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-127">Balance information is calculated as of today.</span></span> | <span data-ttu-id="2b3ac-128">Obecnie system nie wyświetla sald dla okresu naliczania, nawet jeśli zostało to skonfigurowane w parametrach urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-128">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="2b3ac-129">Klauzula prywatności</span><span class="sxs-lookup"><span data-stu-id="2b3ac-129">Privacy notice</span></span>

<span data-ttu-id="2b3ac-130">Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-130">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="2b3ac-131">Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-131">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="2b3ac-132">Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-132">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="2b3ac-133">Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-133">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="2b3ac-134">Informacje te są następnie przekazywane do usługi  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/)  firmy Microsoft, która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-134">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="2b3ac-135">Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-135">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="2b3ac-136">Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-136">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="2b3ac-137">Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-137">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="2b3ac-138">Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług.</span><span class="sxs-lookup"><span data-stu-id="2b3ac-138">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="2b3ac-139">Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-139">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="2b3ac-140">Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2b3ac-140">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="2b3ac-141">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2b3ac-141">See also</span></span> 

[<span data-ttu-id="2b3ac-142">Pobieranie i instalowanie aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b3ac-142">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="2b3ac-143">Centrum pomocy aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b3ac-143">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="2b3ac-144">Zarządzanie wnioskami o urlop w Teams</span><span class="sxs-lookup"><span data-stu-id="2b3ac-144">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

