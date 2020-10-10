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
# <a name="human-resources-app-in-teams"></a>Aplikacja Human Resources w Teams

[!include [banner](includes/preview-feature.md)]

Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams. Aby zażądać informacji, pracownicy mogą współpracować z botem. Zakładka **Czas wolny** zawiera bardziej szczegółowe informacje, a ponadto mogą wysyłać osobom informacje o zbliżającym się czasie wolnym w zespołach i czatach poza aplikacją Human Resources.

![Bot w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-admin-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Karta z prośbą o urlop w Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Instalowanie i konfigurowanie

Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams. Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).

Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Włączanie powiadomień dla aplikacji Human Resources w Teams

Jeśli chcesz, aby użytkownicy otrzymywali powiadomienia o żądaniu urlopu w aplikacji Teams, musisz włączyć powiadomienia w module Human Resources.

>[!NOTE]
>Tylko użytkownicy zalogowani do zespołów i korzystający z aplikacji Human Resources w Teams będą otrzymywali powiadomienia.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz **Łącza**.

3. W obszarze **Konfiguracja** wybierz opcję **Parametry systemowe**.

4. Na karcie **Ogólne** określ ustawienie **Włącz powiadomienia dla aplikacji Teams** na wartość **Tak**.

   ![Włącz powiadomienia aplikacji Teams w parametrach systemowych](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Aby włączyć powiadomienia Teams dla wszystkich użytkowników, wybierz **Tak**, gdy wystąpi monit.

   ![Włącz powiadomienia Teams dla wszystkich użytkowników](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników

Po włączeniu powiadomień dla aplikacji Human Resources w Teams, można włączać lub wyłączać powiadomienia dla poszczególnych użytkowników.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz **Łącza**.

3. W obszarze **Użytkownicy** wybierz **Opcje użytkownika**.

4. Wybierz kartę **Przepływ pracy**.

5. W polu **Włącz powiadomienia dla aplikacji Teams** wybierz wartość **Tak**, aby włączyć powiadomienia dla użytkownika lub **Nie**, aby je wyłączyć.

   ![Włącz powiadomienia aplikacji Teams na karcie przepływ pracy w opcjach użytkownika](./media/hr-admin-teams-leave-app-notifications.png)

6. Wybierz opcję **Zapisz**.

## <a name="known-issues"></a>Znane problemy

| Wystawienie | Stan |
| --- | --- |
| Przewijanie w poziomie nie działa na telefonach Android | Przewijanie w poziomie nie jest problemem na urządzeniach z systemem iOS lub komputerach stacjonarnych. Pracujemy nad poprawką dla Android. |
| Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości. | Prognozowanie nie jest jeszcze dostępne. Jest wyświetlane saldo dla bieżącej daty. |
| Nie można anulować żądań typu **Trwa przegląd**. | Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu. |
| Informacje o saldzie są obliczane na dzień dzisiejszy. | Obecnie system nie wyświetla sald dla okresu naliczania, nawet jeśli zostało to skonfigurowane w parametrach urlopu i nieobecności. |

## <a name="privacy-notice"></a>Klauzula prywatności

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu. Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS). Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/). Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso). Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika. 

Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika. Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources. Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework. 

Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług. Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid i Azure Cosmos DB

Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.

Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams. Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług. Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).

W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams. Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług. Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).
 
Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Informacje dodatkowe 

[Pobieranie i instalowanie aplikacji Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centrum pomocy aplikacji Microsoft Teams](https://support.office.com/teams)</br>
[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md)

