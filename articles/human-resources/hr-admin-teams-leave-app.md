---
title: Aplikacja Human Resources w Teams
description: W tym artykule przedstawiono aplikację Microsoft Dynamics 365 Human Resources w Microsoft Teams.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a7ff576efbfeb0c5383a48756fdd7e79f1abdba2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902264"
---
# <a name="human-resources-app-in-teams"></a>Aplikacja Human Resources w Teams


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Aplikacja Microsoft Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia pracownikom szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams. Aby zażądać informacji, pracownicy mogą współpracować z botem. Karta **Czas wolny** zawiera bardziej szczegółowe informacje. Ponadto mogą wysyłać osobom informacje o zbliżającym się czasie wolnym w zespołach i czatach poza aplikacją Human Resources.

![Bot w aplikacji obsługującej urlopy Human Resources w Teams.](./media/hr-teams-leave-app-bot.png)

![Karta Czas wolny w aplikacji obsługującej urlopy Human Resources w Teams.](./media/hr-teams-leave-app-timeoff-tab.png)

![Karta z prośbą o urlop w Human Resources.](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Instalowanie i konfigurowanie

Aplikację Dynamics 365 Human Resources można znaleźć w sklepie rozwiązania Teams. Aby uzyskać informacje o instalowaniu aplikacji Teams, zapoznaj się z tematem [Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md).

Aby uzyskać informacje dotyczące zarządzania uprawnieniami aplikacji w Teams, zapoznaj się z tematem [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

Jeśli chcesz, aby użytkownicy wyświetlali kalendarz urlopów i nieobecności w aplikacji, musisz włączyć **Kalendarz urlopów i nieobecności w Teams** w zarządzaniu funkcjami w zespołach. Aby uzyskać więcej informacji na temat włączania funkcji, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).

## <a name="update-app"></a>Aktualizacja aplikacji
>[!NOTE]
> Począwszy od 20 grudnia 2021 roku usługi aplikacji Human Resources App hostowane w dzierżawie firmy Microsoft zostaną wyłączone. Nie będzie to miało wpływu na aktualne rozszerzenie (numer 1.1.5), które jest dostępne do instalacji. Główny wpływ będzie to miało na nieaktualne rozszerzenie (wersja 1.1.4). Rozmowa z botem w tej wersji przestanie działać. Karta **Czas pracy** będzie nadal działać w obu rozszerzeniach.

W wersji 1.1.4 rozmówca przestanie odpowiadać na wszelkie wiadomości. Na przykład **Zaloguj się**, **Wyświetl salda** i **Zobacz czas wyłączenia**. Aplikacja musi zostać ręcznie zaktualizowana do najnowszej wersji. Aby uzyskać więcej informacji, zobacz temat [Aktualizacja aplikacji w Microsoft Teams](/MicrosoftTeams/apps-update-experience).

Aby zaktualizować do wersji 1.1.5, wykonaj następujące kroki:
1. W Microsoft Teams przejdź do **aplikacji**.
2. Znajdź aplikację **Human Resources**.
3. Wybierz **Uaktualnianie**.

Wersję aplikacji Human Resources można sprawdzić, przechodząc na kartę **Informacje** lub **Aplikacja osobista**. 

![**Informacje** w aplikacji Human Resources](./media/HR-teams-about.png)

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Włączanie powiadomień dla aplikacji Human Resources w Teams

Jeśli chcesz, aby użytkownicy otrzymywali powiadomienia o żądaniu urlopu w aplikacji Teams, musisz włączyć powiadomienia w module Dynamics 365 Human Resources.

>[!NOTE]
>Tylko użytkownicy zalogowani do zespołów i korzystający z aplikacji Dynamics 365 Human Resources w Teams będą otrzymywali powiadomienia.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz **Łącza**.

3. W obszarze **Konfiguracja** wybierz opcję **Parametry systemowe**.

4. Na karcie **Ogólne** określ ustawienie **Włącz powiadomienia dla aplikacji Teams** na wartość **Tak**.

   ![Włącz powiadomienia aplikacji Teams w parametrach systemowych.](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Aby włączyć powiadomienia Teams dla wszystkich użytkowników, wybierz **Tak**, gdy wystąpi monit.

   ![Włącz powiadomienia Teams dla wszystkich użytkowników.](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników

Po włączeniu powiadomień dla aplikacji Dynamics 365 Human Resources w Teams, można włączać lub wyłączać powiadomienia dla poszczególnych użytkowników.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz **Łącza**.

3. W obszarze **Użytkownicy** wybierz **Opcje użytkownika**.

4. Wybierz kartę **Przepływ pracy**.

5. W polu **Włącz powiadomienia dla aplikacji Teams** wybierz wartość **Tak**, aby włączyć powiadomienia dla użytkownika lub **Nie**, aby je wyłączyć.

   ![Włącz powiadomienia aplikacji Teams na karcie przepływ pracy w opcjach użytkownika.](./media/hr-admin-teams-leave-app-notifications.png)

6. Wybierz opcję **Zapisz**.

## <a name="supported-languages"></a>Obsługiwane języki

Aplikacja Dynamics 365 Human Resources w Teams obsługuje następujące języki:

| Identyfikator lokalizacji | Język |
| --- | --- |
| de-DE | Niemiecki (Niemcy) |
| es-ES | Hiszpański (Hiszpania) |
| es-MX | hiszpański (Meksyk) |
| fr-CA | francuski (Kanada) |
| fr-FR | Francuski (Francja) |
| it-IT | Włoski (Włochy) |
| nl-NL | Holenderski (Holandia) |
| pt-BR | Portugalski (Brazylia) |
| tr-TR | Turecki (Turcja) |
| zh-CN | Chiński (Uproszczony) |

## <a name="notes"></a>Notatki

Następujące elementy pracy są projektowane w przyszłych wersjach:

| Element pracy | Stan |
| --- | --- |
| Saldo jest niepoprawne podczas przesyłania czasu wolnego w przyszłości. | Prognozowanie nie jest jeszcze dostępne. Jest wyświetlane saldo dla bieżącej daty. |
| Nie można anulować żądań typu **Trwa przegląd**. | Ta funkcja nie jest obecnie obsługiwana i zostanie dodana w przyszłym wydaniu. |
| Informacje o saldzie są obliczane na dzień dzisiejszy. | System obecnie nie pokazuje sald z okresu naliczania, nawet jeśli jest skonfigurowany na stronie **Parametry urlopów i nieobecności**. |

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Jeśli użytkownik ma problemy z zalogowaniem się lub użyciem aplikacji Zespoły kadrowe, spróbuj wykonać poniższe instrukcje rozwiązywania problemów. Jeśli nadal masz problemy po diagnostyce, skontaktuj się z pomocą techniczną. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>Sprawdzanie, czy aplikacja Teams Human Resources jest aktualna
Jeśli występują problemy z aplikacją Teams Human Resources, należy sprawdzić, czy jest uruchomiona najnowsza wersja. Minimalna obsługiwana wersja to 1.1.5. Aby uzyskać instrukcje aktualizowania aplikacji Teams, zobacz [dokumentację aplikacji Teams](/MicrosoftTeams/apps-update-experience).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Nie można zalogować się do aplikacji do aplikacji Human Resources w Teams

Jeśli użytkownik kontaktuje się z Tobą, ponieważ nie może zalogować się do aplikacji, należy sprawdzić, czy mają skojarzony rekord pracownika etatowego w module Human Resources.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Błąd podczas zatwierdzania żądań urlopu w aplikacji Human Resources w Teams

Jeśli użytkownik otrzyma komunikat o błędzie podczas próby zatwierdzenia żądań opuszczenia w aplikacji Teams, należy wypróbować następujące kroki rozwiązywania problemów:

1. Sprawdź, czy ich konta programu Teams są takie same, które służą do uzyskiwania dostępu do modułu Human Resources.

2. Sprawdź, czy jest to prawidłowa osoba zatwierdzająca żądanie, sprawdzając ustawienia przepływu pracy do zatwierdzenia urlopu. Aby uzyskać więcej informacji o przepływach pracy wniosków o urlop, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Osoby zatwierdzające urlopy nie otrzymują komunikatów rozmowy Teams, aby zatwierdzać wnioski urlopowe

1. Upewnij się, że powiadomienia są włączone dla środowiska i użytkownika. Więcej informacji znajdziesz w tematach [Włączanie powiadomień dla aplikacji Human Resources w Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) i [Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Upewnij się, że użytkownicy są zalogowani na karcie **Rozmowy** z użyciem tych samych poświadczeń, których używają do zatwierdzania wniosków urlopowych. Użyj komunikatów „wyloguj się”, a następnie „zaloguj się”, aby zalogować się przy użyciu odpowiednich poświadczeń.

3. Jeśli problem będzie nadal występował, sprawdź stan zadania wsadowego **Zdarzenia biznesowe** jako administrator systemu. Jeśli ten etap jest w stanie **oczekiwania** lub **wykonywania**, sprawdź ponownie za kilka minut. Jeśli ten stan pozostanie niezmieniony, zarejestruj bilet pomocy technicznej, aby nasz zespół był w stanie pomóc w rozwiązaniu problemu.

## <a name="privacy-notice"></a>Klauzula prywatności

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Bot aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams analizuje dane wejściowe użytkownika pod kątem zrozumienia zapytania/celu. Dane wprowadzane przez użytkownika, takie jak „Wyszukiwanie konta Contoso”, są kierowane do jednej z usług Microsoft Cognitive Service o nazwie Language Understanding Intelligent Service (LUIS). Przeczytaj więcej o usłudze LUIS [tutaj](https://www.luis.ai/). Usługa LUIS rozróżnia lub interpretuje cel wprowadzenia danych przez użytkownika (w tym przypadku celem jest znalezienie informacji) oraz jednostkę docelową (w tym przypadku zamierzona jednostka to konto o nazwie Contoso). Informacje te są następnie przekazywane do usługi [Azure Bot Framework firmy Microsoft](https://azure.microsoft.com/services/bot-service/), która wchodzi w interakcje z danymi z aplikacji Dynamics 365 Human Resources i pobiera żądane informacje dla zapytania użytkownika.

Instalując bota i zezwalając na dostęp do korzystania z niego, wyrażasz zgodę na to, aby usługa LUIS i usługa Azure Bot Framework przetwarzały cele powiązane z danymi wejściowymi, co skutkuje ulepszoną obsługą funkcji obsługi konwersacji użytkownika. Usługi LUIS i Azure Bot Framework mogą mieć różne poziomy zgodności w porównaniu z aplikacją Dynamics 365 Human Resources. Gdy usługa LUIS ma dostęp tylko do zapytań użytkownika i nie jest przeznaczona do łączenia z danymi lub kontem Dynamics 365 Human Resources użytkownika, użytkownik bota Dynamics 365 Human Resources może dobrowolnie wprowadzić zapytanie zawierające dane klientów, dane osobowe lub inne dane, a taka zawartość zapytania może zostać wysłana do usług LUIS i Azure Bot Framework. 

Zawartość zapytań i wiadomości użytkownika jest przechowywana w systemie LUIS przez maksymalnie 30 dni, jest szyfrowana w stanie spoczynku i nie jest używana do udoskonalania szkoleń lub usług. Przeczytaj więcej informacji na temat usług Cognitive Services [tutaj](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Aby zarządzać ustawieniami administratora dla aplikacji Microsoft Teams, przejdź do [centrum administracyjnego Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid i Azure Cosmos DB

Podczas korzystania z aplikacji Dynamics 365 Human Resources w Microsoft Teams, niektóre dane klientów mogą przepływać poza region geograficzny, w którym wdrożona jest usługa Human Resources Twojego dzierżawcy.

Dynamics 365 Human Resources przesyła szczegóły żądania urlopu pracownika i zadania przepływu pracy do siatki zdarzeń Microsoft Azure i do Microsoft Teams. Dane te mogą być przechowywane w Microsoft Azure Event Grid przez maksymalnie 24 godziny i przetwarzane w Stanach Zjednoczonych. Są szyfrowane w tranzycie i w stanie spoczynku i nie są używane przez firmę Microsoft ani podsystemy do poprawy szkoleń lub usług. Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

W przypadku zawracania do bot rozmowy w aplikacji Human Resources zawartość konwersacji może być przechowywana w Azure Cosmos DB i przekazywana do Microsoft Teams. Te dane mogą być przechowywane w usłudze Azure Cosmos DB przez maksymalnie 24 godziny i mogą być przetwarzane poza regionem geograficznym, w którym wdrożona jest usługa HR dzierżawcy, są szyfrowane podczas przesyłania i w spoczynku i nie są używane przez firmę Microsoft ani jej podprocesorów szkolenia lub ulepszenia usług. Aby zrozumieć miejsce przechowywania danych w Teams, zobacz: [Lokalizacja danych w Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Aby ograniczyć dostęp do aplikacji Human Resources w Microsoft Teams organizacji lub użytkowników w organizacji, należy zapoznać się z tematami [Zarządzanie zasadami uprawnień aplikacji w Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Informacje dodatkowe 

[Pobieranie i instalowanie aplikacji Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centrum pomocy aplikacji Microsoft Teams](https://support.office.com/teams)</br>
[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
