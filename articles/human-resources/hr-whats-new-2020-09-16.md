---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (16 września 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 16 września 2020 roku.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0fe3ac2393e66a00e070d8cb6862c29625d39b53
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6057171"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (16 września 2020 r.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3557. Liczby w nawiasach obok niektórych funkcji odnoszą się do numerów pomocy technicznej Lifecycle Services (LCS).

## <a name="included-in-this-release"></a>Zawarte w tym wydaniu

-  [Zapisane widoki — ogólna dostępność](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- Aby uzyskać więcej informacji, zobacz [Zapisane widoki](../fin-ops-core/fin-ops/get-started/saved-views.md). 

- Formularz **Akcje dotyczące stanowisk** zawiera zaktualizowaną siatkę wymiarów i nowy dialog (469495).

- Jeśli ustawienie **Ogranicz dostęp do informacji o pracownikach** w **Zaawansowanym dostępie** w **Udostępniane parametry Human Resources**, że formularze będą zawierały tylko odpowiednich pracowników (393384).

- Opcje tworzenia nowego kalendarza w jednostce **WorkCalendar** (477055):<br>- Domyślny czas zakończenia<br>-    Domyślny czas rozpoczęcia<br>-  Czy piątek jest dniem roboczym<br>-  Czy poniedziałek jest dniem roboczym<br>-  Czy sobota jest dniem roboczym<br>- Czy niedziela jest dniem roboczym<br>- Czy czwartek jest dniem roboczym<br>- Czy wtorek jest dniem roboczym<br>- Czy środa jest dniem roboczym<br>- Identyfikator dni wolnych od pracy w kalendarzu pracy

- Jednostka **LeaveBankTransactionV1** teraz zawiera kod przyczyny (477823).

- Można teraz zapisać nagrania zadań (492923).

- Dane zostały pomyślnie opublikowane z **HCMWorkerContactEntity** (427620).

- Szybka karta **Wynagrodzenie** jest teraz wyświetlana dla typu pracownika wykonawcy w formularzu **Akcje pracownika** (482494).

- Pola **Poziom** i **Plan** są teraz wymagane w przypadku ustawienia **Stałe wynagrodzenie**. Jeśli pozostawisz te pola puste (482497), zostanie wyświetlony komunikat o błędzie.

- Pole **Typ planu** w ramach **Świadczenia** jest teraz listą rozwijaną (488768).

- Administratorzy systemu otrzymują teraz powiadomienie, jeśli niestandardowe pole zostanie usunięte z Human Resources (481408).

- Podczas procesu kończenia pracy dział Human Resources zachowuje się zgodnie z oczekiwaniami i nie zmienia wybranej firmy po pojawieniu się blokady (479877). 

- Menedżer nie może już dodawać kolumny numerów za pośrednictwem personalizacji (485317).

- Menedżerowi nie można już usunąć filtru zakresu danych z numerów identyfikacyjnych, który utracił ważność (485321).

- Jeślipole **Przełożony do** jest puste, dane dotyczące stanowiska są wyświetlane po umieszczeniu wskaźnika myszy na położeniu (433328).

- Pracownicy mogą teraz wyświetlać informacje o planie świadczeń w Samoobsłudze pracowników (481676).

- Pracownicy mogą teraz wyświetlać wszystkie zarejestrowane kursy (429048).

- Można teraz ograniczyć opcje wyświetlania dla strony **Certyfikaty zawodowe**. Opcje wyświetlania można ograniczyć do bieżącej firmy, stanu pracownika oraz według typu pracownika (451501). 


## <a name="in-preview"></a>W wersji zapoznawczej

### <a name="human-resources-app-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zobacz:

- [Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 1
- [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md) w dokumentacji dot. Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Aplikacja Human Resources w Teams — funkcje w wersji zapoznawczej
 
-  **Powiadomienia**: osoby przesyłające i osoby zatwierdzające żądania czasu wolnego będą powiadamiane w aplikacji Human Resources w Teams. Osoby zatwierdzające mogą zatwierdzać i odmawiać żądania czasu wolnego. Osoby przesyłające będą powiadamiane o zaakceptowaniu lub odrzuceniu żądania. Aby uzyskać więcej informacji, zobacz:
   - [Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 2
   - [Uruchom powiadomienia dla aplikacji Human Resources w Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) w dokumentacji dot. Human Resources
   - [Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) w dokumentacji dot. Human Resources
   - [Powiadomienia Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) w dokumentacji dot. Human Resorces
   - [Wyświetlanie kalendarza urlopu zespołu](./hr-teams-leave-app.md#view-your-teams-leave-calendar) w dokumentacji dot. Human Resorces
 
- **Kalendarz czasu wolnego kierownika**: Kierownicy mogą zobaczyć zatwierdzone i oczekujące prośby o czas wolny dla bezpośrednio podległych pracowników w widoku kalendarza. Ten widok umożliwia w łatwy sposób sprawdzić, kiedy członkowie zespołu mają czas wolny. Aby uzyskać więcej informacji, zobacz:
   - [Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 2
   - [Wyświetlanie kalendarza urlopu zespołu](./hr-teams-leave-app.md#view-your-teams-leave-calendar) w dokumentacji dot. Human Resorces

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych (477004)

Nowa opcja jest teraz dostępna w celu umieszczenia **Elementów pracy przypisanych do mnie** w prawej kolumnie pulpitu nawigacyjnego. W przypadku zmiany wszystkie elementy pracy i listy zadań do wykonania są wyświetlane w tym samym obszarze. Włącz tę funkcję, włączając **Podgląd — udoskonalenia środowiska przepływu pracy** w module Zarządzanie funkcjami. Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

Ta funkcja promuje także opcje przepływu pracy, które znajdują się w formularzach akcji dotyczących pracowników. Opcje przepływu pracy są również wyświetlane powyżej karty działania w ramach szybkiego dostępu. Aby uzyskać więcej informacji, zobacz: 

- [Udoskonalenia środowiska przepływu pracy — zarządzanie organizacją i pracownikami](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) w planie wydawniczym Dynamics 365 2020 wave 2

![Elementy pracy przypisane do mnie](./media/hr-workflow-work-items-assigned-to-me.png)

![Szybki dostęp do elementów przepływu pracy](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>Kalendarz urlopów i nieobecności

Ta wersja zawiera dodatkowe opcje kalendarza dla kalendarzy urlopów i nieobecności. Aby uzyskać więcej informacji, zobacz temat [Wyświetlanie kalendarzy zespołów i firm](./hr-employee-self-service-calendar.md).

## <a name="coming-soon"></a>Wkrótce

### <a name="checklist-entities-included-in-dataverse"></a>Jednostki listy kontrolnej uwzględnione w Dataverse

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

### <a name="benefits-management-reason-codes"></a>Kody przyczyn zarządzania korzyściami

Kody przyczyn zarządzania korzyściami zostaną wkrótce połączone z istniejącymi kodami przyczyn w Human Resources. Jeśli kody przyczyn zostały utworzone w ramach zarządzania świadczeniami o długości przekraczającej 15 znaków, należy zmienić nazwę kodu przyczyny w formularzu **Kody przyczyn** na nazwę zawierającą 15 lub mniej znaków. Po zaktualizowaniu nazwy kod przyczyny pojawi się pod istniejącym formularzem w module Zarządzanie kadrami. Ta zmiana będzie dostępna w przyszłości i nie będzie miała wpływu na istniejącą funkcję.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
