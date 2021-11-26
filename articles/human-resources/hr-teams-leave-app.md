---
title: Zarządzanie wnioskami o urlop w Teams
description: W tym temacie przedstawiono sposób wysyłania wniosku o urlop w aplikacji Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 10538c96a7637a95c60beef40a02fdb5432959ec
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771538"
---
# <a name="manage-leave-requests-in-teams"></a>Zarządzanie wnioskami o urlop w Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Aplikacja Dynamics 365 Human Resources w rozwiązaniu Microsoft Teams umożliwia szybkie wysyłanie wniosku o urlop i wyświetlanie informacji dotyczących bilansu nieobecności w rozwiązaniu Microsoft Teams. Możesz wejść w interakcję z botem, aby poprosić o informacje i złożyć wniosek o urlop. Karta **Czas wolny** zawiera bardziej szczegółowe informacje. Możesz też wysyłać użytkownikom informacje o zbliżającym się czasie wolnym w Teams i na czatach poza aplikacją Human Resources.

## <a name="install-the-app"></a>Instalowanie aplikacji

Aplikację Dynamics 365 Human Resources można znaleźć w sklepie rozwiązania Teams.

1. W Microsoft Teams przejdź do listy aplikacji.
 
2. Wyszukaj aplikację Dynamics 365 Human Resources, a następnie wybierz kafelek **Human Resources**.

3. Wybierz przycisk **Dodaj**, aby zainstalować aplikację.

Jeśli aplikacja nie zaloguje Cię automatycznie, wybierz kartę **Ustawienia**, aby się zalogować.

> [!NOTE]
> Jeśli nie widzisz okna logowania, zaktualizuj ustawienia przeglądarki, aby zezwalać na wyskakujące okienka. 

Jeśli masz dostęp do więcej niż jednego wystąpienia aplikacji Human Resources, możesz wybrać środowisko, z którym chcesz się połączyć, na karcie **Ustawienia**.

> [!NOTE]
> Aplikacja obsługuje teraz rolę zabezpieczeń administratora systemu.
 
## <a name="use-the-bot"></a>Korzystanie z bota

Po zainstalowaniu aplikacji zostanie wyświetlony komunikat powitalny informujący o typach akcji, które bot może wykonać w Twoim imieniu.

> [!NOTE]
> Kiedy po raz pierwszy wchodzisz w interakcję z botem, być może będziesz musiał się zalogować. Jeśli nie widzisz okna logowania, zaktualizuj ustawienia przeglądarki, aby zezwalać na wyskakujące okienka.

Możesz poprosić bota o wykonanie następujących zadań:

- Zobacz swoje aktualne salda urlopów. Na przykład wyślij wiadomość o treści „Wyświetlanie salda urlopów”.

- Uruchomienie wniosku o urlop w Twoim imieniu. Na przykład, wyślij wiadomość o treści „Weź wolne” lub „Chcę wziąć wolne w następny czwartek i piątek”, aby być bardziej konkretnym w żądaniu urlopu dla typu urlopu. 

  ![Rozpoczynanie rozmowy z wnioskami o urlop w Teams.](./media/hr-teams-leave-app-initiate.png)

- Bot czatu wypełni dla Ciebie prośbę o urlop. Wybierz opcję **Żądanie czasu wolnego** i edytuj szczegóły swojego żądania.

   Aby przesłać wnioski urlopowe dotyczące wielu typów urlopów dla tej samej daty, wybierz z menu **Więcej opcji** opcję **Podziel dzień**. 

   Jeśli wybierzesz urlop na pół dnia, a jednostką wniosku o urlop są dni, możesz określić, czy chcesz wnioskować o wolne za pierwsze pół dnia, czy za drugie pół dnia, wybierając opcję **Definicja połowy dnia** z menu **Więcej opcji**.
   
   ![Definicje połowy dnia.](./media/HalfDayDefinitions.png)

- Po zakończeniu edytowania szczegółów wniosku urlopowego wybierz opcję **Prześlij**, aby przesłać go do zatwierdzenia.

  ![Przesyłanie wniosku urlopowego.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Zarządzanie urlopami w Teams

Na karcie **Czas wolny** można wyświetlić następujące informacje: 

- Informacje na temat bilansu dla każdego typu urlopu, w którym Cię zarejestrowano

- Nadchodzące wnioski o urlop

- Żądania czasu wolnego

- Wnioski o urlopu w wersji roboczej
 
### <a name="create-a-new-request"></a>Tworzenie nowego wniosku

1. Aby utworzyć nowy wniosek o urlop, wybierz pozycję **Nowy wniosek**.

2. Wprowadź dzień lub dni, w które chcesz wziąć urlop, a następnie wybierz pozycję **Dodaj**.

   ![Dodawanie czasu wolnego w aplikacji obsługującej urlopy Human Resources w Teams.](./media/TimeOffHours.png)

3. Wprowadź kod przyczyny, jeśli ma on zastosowanie. Wprowadź komentarze i dodaj załączniki.

4. Jeśli chcesz przesłać kilka wniosków o urlop na tę samą datę dla różnych typów urlopu., wybierz z menu **Więcej opcji** opcję **Podziel dzień**.

5. Wybierz opcję **Definicja połowy dnia**, aby określić, czy chcesz złożyć wniosek o pierwszą połowę, czy drugą połowę dnia wolnego. Ta opcja jest dostępna w przypadku, gdy jednostka wniosku urlopowego jest w dniach, a wnioskowana ilość wynosi 0,5 dnia.

6. Po zakończeniu wprowadzania informacji wybierz **Prześlij**, aby przesłać wniosek do zatwierdzenia. Możesz również wybrać **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.

### <a name="manage-draft-requests"></a>Zarządzanie wnioskami w wersji roboczej

1. Wybierz kartę **Wersje robocze**.

2. Wybierz symbol ołówka, aby edytować wniosek, lub symbol kosza, aby usunąć wniosek.

3. Wprowadź potrzebne zmiany. Po zakończeniu wprowadzania informacji wpisz **Prześlij**, aby przesłać wniosek do zatwierdzenia. Możesz również wybrać pozycję **Zapisz jako wersję roboczą**, aby wrócić do wniosku później.
   
### <a name="respond-to-teams-notifications"></a>Odpowiadanie na powiadomienia Teams

Gdy użytkownik lub pracownik, dla którego użytkownik jest osobą zatwierdzającą prześle wniosek urlopowy, użytkownik otrzyma powiadomienie w aplikacji Human Resources w Teams. Możesz wybrać powiadomienie, aby wyświetlić wniosek urlopowy. Powiadomienia są również wyświetlane w obszarze **Czatu**.

Jeśli jesteś osobą zatwierdzającą, możesz wybrać opcję **Zatwierdzanie** lub **Odmowa** w powiadomieniu. Można również podać opcjonalny komunikat.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Wysyłanie nadchodzących informacji o czasie do współpracujących

Po zainstalowaniu aplikacji Human Resources dla Teams można łatwo wysyłać do współpracowników zespołów lub rozmów informacje o zbliżającym się czasie pracy.

1. W zespole lub rozmowę w Teams wybierz przycisk Human Resources poniżej okna rozmowy.

   ![Przycisk Human Resources poniżej okna rozmowy.](./media/hr-teams-leave-app-chat-button.png)

2. Wybierz żądanie opuszczenia, które chcesz udostępnić. Jeśli chcesz udostępnić wersję roboczą wniosku urlopowego, najpierw wybierz opcję **Wersje robocze**.

Twoje żądanie opuszczenia będzie wyświetlane w rozmowie.

Jeśli udostępniono wersję roboczą żądania, będzie ona wyświetlana jako wersja robocza.

## <a name="view-your-teams-leave-calendar"></a>Wyświetlanie kalendarza urlopów zespołu

Jeśli jesteś menedżerem z bezpośrednimi podwładnymi, możesz wyświetlić zatwierdzony i oczekujący urlop zespołu.

1. W aplikacji zasoby ludzkie w zespołach wybierz opcję **Czas wolny**.

2. Wybierz **Kalendarz zespołu**. W kalendarzu są wyświetlane zatwierdzone i oczekujące urlopy bezpośrednich podwładnych.

   > [!NOTE]
   > Jeśli nie możesz zobaczyć kalendarza zespołu, poproś administratora o jego włączenie. Aby uzyskać więcej informacji, zobacz temat [Instalowanie i konfigurowanie](hr-admin-teams-leave-app.md#install-and-setup).

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

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Jeśli masz problemy z zalogowaniem się lub użyciem aplikacji Dynamics 365 Human Resources w aplikacji Teams, spróbuj wykonać poniższe instrukcje rozwiązywania problemów. Jeśli nadal masz problemy po diagnostyce, skontaktuj się z pomocą techniczną. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Nie można zalogować się do aplikacji do aplikacji Human Resources w Teams

Jeśli nie możesz zalogować się do aplikacji, być może konto używane do logowania w Microsoft Teams nie jest skojarzone z rekordem pracownika w rozwiązaniu Dynamics 365 Human Resources. Skontaktuj się z administratorem systemu, aby upewnić się, że rekord pracownika jest poprawnie skojarzony.

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>Nie można odnaleźć środowiska Dynamics 365 Human Resources w ustawieniach

Jeśli nie możesz wybrać prawidłowego środowiska Dynamics 365, rekord użytkownika mógł nie zostać poprawnie zsynchronizowany. Skontaktuj się z administratorem systemu, aby ponownie utworzyć rekord użytkownika i powiązać go z poświadczeniami użytkownika. Następnie spróbuj zalogować się do aplikacji Human Resources dla Microsoft Teams za kilka minut.

### <a name="translations-dont-display-correctly"></a>Tłumaczenia nie są wyświetlane prawidłowo

Jeśli tłumaczenia nie są wyświetlane zgodnie z oczekiwaniami, upewnij się, że język wybrany w aplikacji Teams jest zgodny z językiem wybranym w **Opcjach użytkownika** zasobów ludzkich.

W zespołów sprawdź **Język aplikacji** w **Ustawieniach**.

![Ustawienia Teams.](./media/hr-teams-leave-app-settings.png)

W menu Zasoby ludzkie wybierz pozycję **Ustawienia**, a następnie wybierz **Opcje użytkownika**. Upewnij się, że pole **Język** pasuje do pola **Języka aplikacji** w Teams.

![Opcje użytkownika w Human Resources.](./media/hr-teams-leave-app-user-options.png)

Jeśli nadal wystąpią problemy z tłumaczeniami, poinformuj nas o tym. Aby uzyskać więcej informacji, przejrzyj temat [Uzyskaj pomoc techniczną dla aplikacji Finance and Operations lub usług Lifecycle Services (usługi LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Błąd podczas zatwierdzania żądań urlopu w aplikacji Human Resources w Teams

Jeśli otrzymasz komunikat o błędzie podczas próby zatwierdzenia wniosków o urlop w aplikacji Teams, wykonaj następujące kroki, aby rozwiązać problem:

1. Sprawdź, czy konto używane do logowania Microsoft Teams jest takie samo, którego używasz w celu uzyskania dostępu do rozwiązania Dynamics 365 Human Resources.

2. Sprawdź, czy jesteś prawidłową osobą zatwierdzającą żądanie, sprawdzając ustawienia przepływu pracy do zatwierdzenia urlopu. Aby uzyskać więcej informacji o przepływach pracy wniosków o urlop, zobacz temat [Tworzenie przepływu pracy wniosku o urlop](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Osoby zatwierdzające urlopy nie otrzymują komunikatów rozmowy Teams, aby zatwierdzać wnioski urlopowe

1. Upewnij się, że powiadomienia są włączone dla środowiska i użytkownika. Więcej informacji znajdziesz w tematach [Włączanie powiadomień dla aplikacji Human Resources w Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) i [Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Upewnij się, że użytkownicy są zalogowani na karcie **Rozmowy** z użyciem tych samych poświadczeń, których używają do zatwierdzania wniosków urlopowych. Użyj komunikatów „wyloguj się”, a następnie „zaloguj się”, aby zalogować się przy użyciu odpowiednich poświadczeń.

3. Jeśli problem będzie nadal występował, sprawdź stan zadania wsadowego **Zdarzenia biznesowe** jako administrator systemu. Jeśli ten etap jest w stanie **oczekiwania** lub **wykonywania**, sprawdź ponownie za kilka minut. Jeśli ten stan pozostanie niezmieniony, zarejestruj bilet pomocy technicznej, aby nasz zespół był w stanie pomóc w rozwiązaniu problemu.

## <a name="known-accessibility-issues"></a>Znane problemy dotyczące ułatwień dostępu

W aplikacji Human Resources w Teams pojawiają się następujące problemy ułatwień dostępu (zostaną one naprawione w kolejnych wersjach aplikacji).

| Wystawienie | Obejście lub wyjaśnienie problemu |
| --- | --- |
| Powiększenie do 400% na pulpicie powoduje ukrycie niektórych przycisków akcji. | Zaleca się używanie lupy zamiast powiększenia do czasu, aż usuniemy problemy z tym poziomem powiększenia. |
| Na karcie **Czas wolny** funkcja VoiceOver podczas odczytywania nagłówka siatki czasu wolnego informuje o akcji powiązanej z przyciskiem. | Nagłówek i elementy siatki są grupowane według lat i można je zwinąć. VoiceOver interpretuje tę prezentację jako element praktyczny, ale tak nie jest. |
| Na karcie **Czas wolny** podczas przechodzenia do **Kodu przyczyny** w nowym wniosku uruchamia się dodatkowy gest przeciągnięcia. | Nie ma żadnego ukrytego formantu, do którego można uzyskać dostęp za pomocą tego gestu przeciągnięcia. |
| Przy otwartym kalendarzu przeciągnięcie palcem na karcie **Czas wolny** prowadzi do obszaru poza formantem, zamiast na górę nowego wniosku lub do trybu edycji wniosku. | Kiedy dojdziesz do opcji **Przejdź do dzisiaj**, potraktuj tę pozycję jako koniec formantu i przesuń palcem w odwrotnym kierunku, aby wrócić na górę strony. |
| Na karcie **Czatu** podczas wpisywania daty przy użyciu narzędzia wspomagającego lub nawigacji z klawiatury obraz przeskakuje na górę strony. | Naciskaj klawisz Tab, aż przejdziesz z powrotem do obszaru wpisywania wiadomości. |

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
[Aplikacja Human Resources w Teams](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
