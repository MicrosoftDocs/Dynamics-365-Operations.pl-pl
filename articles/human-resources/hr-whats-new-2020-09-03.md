---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (03 września 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 3 września 2020 roku.
author: andreabichsel
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 41763a8817d0c39b14284a247cf3e46678e7811b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130864"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (3 września 2020 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Zmiany dotyczą kompilacji o numerze 8.1.3504. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Lifecycle Services (LCS).

Aby uzyskać więcej informacji o nadchodzących funkcjach w module Human Resources, zapoznaj się [z omówieniem Dynamics 365 Human Resources 2019 release wave 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). Aby uzyskać więcej informacji na temat procesu aktualizacji dla modułu Human Resources, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>W tej wersji

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Nowa siatka i wzorzec okna dialogowego dla wymiarów finansowych są ustawiane w całym module Human Resources (469495)

Nowy wzorzec wymiarów finansowych jest teraz dostępny w następujących obszarach:

- Akcje dotyczące stanowisk (formularz: **HcmPositionActionDetail**)
- Kody zarobków dla listy płac (formularz: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>Wpisy nie pojawiają się w kalendarzu wystawiania w firmie, jeśli nie są włączone rozszerzenia kalendarza urlopu i nieobecności (484406)

Ta wersja dotyczy rozwiązania problemów, w przypadku których wpisy urlopowe nie są wyświetlane w kalendarzu urlopów firmy. Ten problem występuje tylko wtedy, gdy opcja zarządzania funkcjami **Ulepszenia kalendarza nieobecności i urlopów** nie jest włączona.

### <a name="benefitplanemployeeentity-issue-467597"></a>Problem z BenefitPlanEmployeeEntity (467597)

Ta wersja koryguje problem dotyczący encji **BenefitsPlanEmployee**. Podczas importowania rejestracji pracowników **Kod objęcia świadczeniem** i **Kod typu planu** są ustawiane poprawnie. Ten błąd powodował, że plany świadczeń pracowniczych były wyświetlane niepoprawnie w formularzach **Plan świadczeń pracownika** i **Otwarcie rejestracji** w module samoobsługowym pracownika.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>Plik elektroniczny 1094-C — brakuje litery w XML (435190)

Ta zmiana polega na usunięciu problemu dotyczącego pliku wyjściowego 1094-C — brak znaku wymaganego podczas przesyłania do urzędu skarbowego.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Tabela wynagrodzeń pracownika o zmiennej wysokości mapowana na formę stałego wynagrodzenia (476117)

Ta zmiana powoduje wyrównanie pól stałych wynagrodzeń za pomocą formularza stałego wynagrodzenia. Pola wynagrodzeń o zmiennej wysokości są teraz dostępne tylko w formularzu wynagrodzeń o zmiennej wysokości.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>Prośby o urlop były możliwe przed rejestracją, jeśli typ urlopu zawierał ujemne saldo minimalne (469917)

Ta zmiana uniemożliwia wprowadzanie żądań urlopu przed zarejestrowaniem w planie, nawet jeśli rejestracja ma ujemne salda minimalne. Można wprowadzać i przesyłać tylko żądania, gdy plan jest aktywny.

### <a name="document-templates-dont-download-457279"></a>Szablony dokumentów nie pobierają się (457279)

Można teraz pobrać wszystkie szablony dokumentów. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>Dane są wyświetlane jako nagłówki kolumn zamiast wierszy w polu stawka płacy w raporcie planu wynagrodzeń (476077)

W raporcie analizy są teraz wyświetlane poprawne informacje o **Stawce wynagrodzenia**.

## <a name="in-preview"></a>Wersja próbna

### <a name="human-resources-application-in-teams"></a>Aplikacja Human Resources w Teams

Pracownicy mogą wyświetlać i żądać czasu poza pracą w ramach Microsoft Teams. Mogą oni współpracować z botem, aby tworzyć żądania urlopu. Aby uzyskać więcej informacji, zobacz:

- [Urlop i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 1
- [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841) w dokumentacji dot. Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Aplikacja Human Resources w Teams — funkcje w wersji zapoznawczej
 
-  **Powiadomienia**: osoby przesyłające i osoby zatwierdzające żądania czasu wolnego będą powiadamiane w aplikacji Human Resources w Teams. Osoby zatwierdzające będą mogły zatwierdzać i odmawiać żądania czasu wolnego. Osoby przesyłające będą powiadamiane o zaakceptowaniu lub odrzuceniu żądania. Aby uzyskać więcej informacji, zobacz:
   - [Urlop i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 2
   - [Uruchom powiadomienia dla aplikacji Human Resources w Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) w dokumentacji dot. Human Resources
   - [Włączanie i wyłączanie powiadomień Teams dla poszczególnych użytkowników](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) w dokumentacji dot. Human Resources
   - [Powiadomienia Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) w dokumentacji dot. Human Resorces
   - [Wyświetlanie kalendarza urlopu zespołu](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) w dokumentacji dot. Human Resorces
 
- **Kalendarz czasu wolnego kierownika**: Kierownicy będą mogli zobaczyć zatwierdzone i oczekujące prośby o czas wolny dla bezpośrednio podległych pracowników w widoku kalendarza. Ten widok umożliwia w łatwy sposób sprawdzić, kiedy członkowie zespołu mają czas wolny. Aby uzyskać więcej informacji, zobacz:
   - [Urlop i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) w planie rozwiązania Dynamics 365 2020 aktualizacja 2
   - [Wyświetlanie kalendarza urlopu zespołu](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) w dokumentacji dot. Human Resorces

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych (477004)

Nowa opcja jest teraz dostępna w celu umieszczenia **Elementów pracy przypisanych do mnie** w prawej kolumnie pulpitu nawigacyjnego. W przypadku zmiany wszystkie elementy pracy i listy zadań do wykonania są wyświetlane w tym samym obszarze. Włącz tę funkcję, włączając **Podgląd — udoskonalenia środowiska przepływu pracy** w module Zarządzanie funkcjami. Aby uzyskać informacje na temat włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

Ta funkcja promuje także opcje przepływu pracy, które znajdują się w formularzach akcji dotyczących pracowników. Opcje przepływu pracy są również wyświetlane powyżej karty działania w ramach szybkiego dostępu. Aby uzyskać więcej informacji, zobacz: 

- [Udoskonalenia środowiska przepływu pracy — zarządzanie organizacją i pracownikami](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) w planie wydawniczym Dynamics 365 2020 wave 2

![Elementy pracy przypisane do mnie](./media/hr-workflow-work-items-assigned-to-me.png)

![Szybki dostęp do elementów przepływu pracy](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Wkrótce

### <a name="checklist-entities-included-in-dataverse"></a>Jednostki listy kontrolnej uwzględnione w Dataverse

Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

### <a name="benefits-management-reason-codes"></a>Kody przyczyn zarządzania korzyściami

Kody przyczyn zarządzania korzyściami zostaną wkrótce połączone z istniejącymi kodami przyczyn w Human Resources. Jeśli kody przyczyn zostały utworzone w ramach zarządzania świadczeniami o długości przekraczającej 15 znaków, należy zmienić nazwę kodu przyczyny w formularzu **Kody przyczyn** na nazwę zawierającą 15 lub mniej znaków. Po zaktualizowaniu nazwy kod przyczyny pojawi się pod istniejącym formularzem w module Zarządzanie kadrami. Ta zmiana będzie dostępna w przyszłości i nie będzie miała wpływu na istniejącą funkcję.

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2019, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]