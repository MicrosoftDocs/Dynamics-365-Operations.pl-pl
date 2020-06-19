---
title: Zarządzanie wnioskami o urlop w Teams
description: W tym temacie przedstawiono sposób wysyłania wniosku o urlop w aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
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
ms.openlocfilehash: b3daa76385518ad4c7150fa93ce33be0351bfd57
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428835"
---
# <a name="manage-leave-requests-in-teams"></a>Zarządzanie wnioskami o urlop w Teams

[!include [banner](includes/preview-feature.md)]

Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams. Aby zażądać informacji, możesz współpracować z botem. Karta **Czas wolny** zawiera bardziej szczegółowe informacje.

## <a name="install-the-app"></a>Instalowanie aplikacji

Aplikację Human Resources można znaleźć w sklepie rozwiązania Teams.

1. W rozwiązaniu Microsoft Teams wybierz symbol wielokropka.

   ![Symbol wielokropka w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. Wyszukaj aplikację Dynamics 365 Human Resources, a następnie wybierz kafelek **Human Resources**.

   ![Kafelek HR w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. Wybierz przycisk **Dodaj**, aby zainstalować aplikację.

   ![Instalacji aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-in-store.png)

Jeśli aplikacja nie zaloguje Cię automatycznie, wybierz kartę **Ustawienia**, aby się zalogować.

![Karta Ustawienia w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka. 

Jeśli masz dostęp do więcej niż jednego wystąpienia aplikacji Human Resources, możesz wybrać środowisko, z którym chcesz się połączyć, na karcie **Ustawienia**.

> [!WARNING]
> Aplikacja nie obsługuje obecnie roli zabezpieczeń Administrator systemu i będzie wyświetlać komunikat o błędzie, jeśli zalogujesz się przy użyciu konta administratora systemu. Aby zalogować się przy użyciu innego konta, na karcie **Ustawienia** wybierz przycisk **Przełącz konta**, a następnie zaloguj się przy użyciu konta użytkownika, które nie ma uprawnień administratora systemu.
 
## <a name="use-the-bot"></a>Korzystanie z bota

Po zainstalowaniu aplikacji zostanie wyświetlony komunikat powitalny informujący o typach akcji, które bot może wykonać w Twoim imieniu.

![Komunikat powitalny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> Podczas pierwszej interakcji z botem być może trzeba będzie się zalogować. Jeśli nie widzisz okna dialogowego logowania, sprawdź ustawienia przeglądarki, aby zezwolić na wyskakujące okienka.

Możesz poprosić bota o wykonanie następujących zadań:

- Wyświetlenie bilansu nieobecności dla każdego typu urlopu, w którym Cię zarejestrowano.

   ![Pokazywanie bilansów w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- Wyświetlenie dodatkowych szczegółów dotyczących określonego typu urlopu.

   ![Pokazywanie szczegółów w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-details.png)

- Uruchomienie wniosku o urlop w Twoim imieniu.

   ![Wysyłanie wniosków o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-request.png)
 
Po rozpoczęciu wniosku o urlopu można skorygować dni bezpośrednio na karcie lub wybrać pozycję **Edytuj szczegóły**, aby dodać dodatkowe informacje do wniosku.

![Edytowanie wniosku o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-edit.png)
 
Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia. Możesz również wpisać **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.

![Przesyłanie wniosku o urlop w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Zarządzanie urlopami w Teams

Na karcie **Czas wolny** można wyświetlić następujące informacje:

- Informacje na temat bilansu dla każdego typu urlopu, w którym Cię zarejestrowano

- Nadchodzące wnioski o urlop

- Wnioski dotyczące czasu wolnego

- Wnioski o urlopu w wersji roboczej

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Tworzenie nowego wniosku

1. Aby utworzyć nowy wniosek o urlop, wybierz pozycję **Nowy wniosek**.

   ![Nowy wniosek w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Wprowadź dzień lub dni, w które chcesz wziąć urlop, a następnie wybierz pozycję **Dodaj**.

   ![Dodawanie czasu wolnego w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Wprowadź kod przyczyny, jeśli ma on zastosowanie. Wprowadź komentarze i dodaj załączniki.

4. Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia. Możesz również wpisać **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.

### <a name="manage-draft-requests"></a>Zarządzanie wnioskami w wersji roboczej

1. Wybierz kartę **Wersje robocze**.

   ![Karta Wersje robocze w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. Wybierz symbol ołówka, aby edytować wniosek, lub symbol kosza, aby usunąć wniosek.

3. Wprowadź potrzebne zmiany. Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia. Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.

   ![Edytowanie wersji roboczej w aplikacji obsługującej urlopy Human Resources w Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a>Klauzula prywatności

Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu. Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS). Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/). Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso). Informacje te są następnie przekazywane do usługi  [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/)  firmy Microsoft, która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika. 

Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika. Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources. Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework. 

Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług. Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Informacje dodatkowe

[Pobieranie i instalowanie aplikacji Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centrum pomocy aplikacji Microsoft Teams](https://support.office.com/teams)</br>
[Aplikacja Human Resources w Teams](hr-admin-teams-leave-app.md)
