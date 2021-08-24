---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (20 sierpnia 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 20 sierpnia 2020 roku.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 32535c1f93990306ffaa0a5d97b48d3e6fdda7d014ceeeb2552960cd08b4be6c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775850"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (20 sierpnia 2020 r.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3478. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Umożliwia wyświetlenie kart informacji dotyczących nadchodzącego i oczekującego urlopu w obszarze roboczym Osoby

Opcje nadchodzącego i oczekującego urlopu są dostępne na kartach urlop i nieobecność w obszarze roboczym **Osoby**.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>Pole prywatne nie jest ustawione domyślnie na „tak” w przypadku roli pracownika w samoobsłudze pracownika (477106)

Pole **Prywatne** jest domyślnie ustawione na wartość **Tak**, gdy pracownicy dodają nowe rekordy adresów za pomocą strony **Informacje osobiste** w samoobsłudze pracowników. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>Skrócona karta Kandydaci do zatrudnienia w sekcji Zarządzania kadrami wyświetla niepoprawną liczbę kandydatów (470110)

Na stronie **Zarządzanie personelem** jest teraz wyświetlana poprawna liczba kandydatów do zatrudnienia. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>Nie można wprowadzić choroby dla byłego pracownika, jeśli w naliczeniu ustawiono wartość zero (446195)

Transakcje urlopowe są teraz dozwolone dla pracowników, którzy zostali zwolnieni w przyszłości, a naliczenie jest ustawione na zero. Transakcje urlopowe mogą być wprowadzane aż do momentu daty zakończenia zatrudnienia pracownika etatowego. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>Dodanie pól niestandardowych do nowego formularza powoduje wyłączenie pól w okienku akcji dotyczącego zarządzania urlopem (473314)

Opcje okienka akcji w nowym formularzu **Pracownik** w obszarze **Zarządzanie urlopem** nie będą już wyłączane, jeśli dodano pola niestandardowe do nowego formularza **Pracownik**.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Wprowadzenie obowiązkowości wypełnienia komentarza pola urlopowego pozwala na przesłanie żądania urlopowego, nawet gdy nie ma żadnego komentarza (473543)

Pole komentarza jest wymagane i należy je wypełnić przed zamknięciem procesu. Pola wymagane to funkcja w wersji zapoznawczej.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Jednostka DMF dostępna dla wstrzymań naliczania

Jednostka DMF jest teraz dostępna dla wstrzymań naliczania.

## <a name="in-preview"></a>Wersja próbna

### <a name="mandatory-fields"></a>Pola obowiązkowe

Można wprowadzać wymagane pola, korzystając z możliwości personalizacji zasobów ludzkich. Ta funkcja wymaga **Zapisanych widoków**. Aby uzyskać więcej informacji na temat zapisanych widoków, zobacz:

- [Zapisane widoki — ogólna dostępność](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) w planie wydania Dynamics 365 2020 aktualizacja 2
- [Tworzenie formularzy, które w pełni wykorzystują zapisane widoki](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zobacz:

- [Urlop i nieobecność pracowników w Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 1
- [Aplikacja Human Resources w Teams](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a>Wkrótce

### <a name="human-resources-app-in-teams-preview-features"></a>Aplikacja Human Resources w Teams — funkcje w wersji zapoznawczej
 
-  **Powiadomienia**: osoby przesyłające i osoby zatwierdzające żądania czasu wolnego będą powiadamiane w aplikacji Human Resources w Teams. Osoby zatwierdzające będą mogły zatwierdzić lub odmówić żądanie czasu wolnego, a osoby przesyłające otrzymają powiadomienie o zatwierdzeniu lub odrzuceniu żądania.
 
- **Kalendarz czasu wolnego kierownika**: Kierownicy będą mogli zobaczyć zatwierdzone i oczekujące prośby o czas wolny dla bezpośrednio podległych pracowników w widoku kalendarza. Ten widok umożliwia w łatwy sposób sprawdzić, kiedy członkowie zespołu mają czas wolny.

### <a name="checklist-entities-included-in-dataverse"></a>Jednostki listy kontrolnej uwzględnione w Dataverse

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

## <a name="known-issues"></a>Znane problemy

W obszarze roboczym **Zarządzanie funkcjami** mogą być wyświetlane funkcje, które są wyłączone w postaci funkcji podglądu, gdy są one zazwyczaj dostępne. Poniżej znajduje się lista ogólnie dostępnych funkcji, które pokazują nieprawidłowy stan. 

- Zarządzanie świadczeniami
- Zarządzanie sprawami
- Rejestrowanie z bazie danych (inspekcja)
- Naliczanie urlopów dla jednej firmy lub pojedynczego planu
- Zawieszenie naliczania urlopów i nieobecności
- Kod przyczyny korekty salda i komentarz
- Kupuj i sprzedawaj urlop
- Kalendarz urlopów i nieobecności
- Reguły przeniesienia na następny okres urlopu
- Inspekcja naliczania urlopów
- Usunięcie naliczenia urlopów
- Zaokrąglanie naliczania urlopów
- Konfiguruj wiele typów urlopów w jednym planie urlopów
- Aktualizuj udoskonalenia czasu wolnego
- Użyj równoważnika pełnego etatu pracownika etatowego do naliczeń
- Widok wynagrodzeń między firmami
- Drukowanie przeglądów wydajności
- Świąteczne korekty naliczania nieobecności

### <a name="benefit-plan-employee-entity"></a>Encja planu świadczeń pracownika 

Ostatnio wykryto dwa problemy dotyczące encji **BenefitsPlanEmployee**. Podczas importowania rejestracji pracowników **Kod objęcia świadczeniem** i **Kod typu planu** są ustawiane niepoprawnie. Ten błąd powoduje, że plany świadczeń pracowniczych są wyświetlane niepoprawnie w formularzu **Plan świadczeń pracownika** i w formularzu **Otwarcie rejestracji** w module samoobsługowym pracownika. Ten problem może również wpływać na zdolność pracownika do wyboru planów w module samoobsługowym. Obecnie nie ma rozwiązania tego problemu. Ta poprawka jest traktowana jako poprawka o wysokim priorytecie i zostanie wydana w następnej wersji oprogramowania.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]