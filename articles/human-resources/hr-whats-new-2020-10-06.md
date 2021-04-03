---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (6 października 2020 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 6 października 2020 roku.
author: jcart1106
manager: tfehr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 330b037e2ba50ed090fd41b0990d6cf37d9d8b01
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463557"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources (6 października 2020 r.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources. Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3636.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Dodatkowe szczegółowe informacje na temat wystawiania kalendarzy | [Zapewnij dodatkowe informacje o widokach kalendarza urlopów](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Wyświetlanie kalendarza zespołów i firm](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

>[!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie | opis |
| --- | --- | --- |
| 448806 | **Domyślny typ identyfikacji** — Eksportowanie jako **Identyfikator RecId** w parametrach HCM | Ta zmiana jednostki Parametry modułu Human Resources powoduje dodanie dodatkowej kolumny, w której jest wyświetlany **Domyślny typ identyfikacji**. |
| 492923 | Nagrania zadań nie są zapisywane w Lifecycle Services (LCS) | Nagrania zadań można teraz zapisać w LCS. |
| 429950 | Stałe wynagrodzenie nie wygasa poprawnie podczas zmieniania pozycji | Zmiana pozycji pracownika na stronie **Przeniesienie pracownika** powoduje, że data końcowa wynagrodzenia została ustawiona na jeden dzień przed końcem stanowiska. Data zakończenia wynagrodzenia jest teraz taka sama jak data zakończenia pozycji. |
| 467214 | **Analiza wynagrodzeń** jest wyświetlana tylko w przypadku, gdy dla **Nazwy konwersji stawki płac** jest ustawiona wartość **roczna** | Płacone stawki płacowe o nazwie innej niż **Roczna** nie zostały wyświetlone w analizie wynagrodzeń. W przypadku tej aktualizacji analiza wynagrodzeń używa teraz wszystkich konwersji stawek wynagrodzeń. Gdy raporty są wykonywane według **Godzinowe** lub **Wynagrodzenie**, w filtrze **wynagrodzeń** są uwzględniane wszystkie konwersje stawek płacowych używające okresu innego niż godziny. Tylko stawki płacy z okresem **Godzinowe** są uwzględniane w filtrze **Godzinowym**. |
| 482464 | Podczas przeglądania **Eecenzji** widok **Szczegółów** nie zmienia się w widok siatki po zastosowaniu filtru | Po zastosowaniu filtru siatka przeglądy jest wyświetlana zgodnie z oczekiwaniami. |
| 483184 | W module zasoby ludzkie nie są generowane naliczenia urlopu, jeśli zostanie wybrana opcja **Podstawa poziomu** jako **skorygowana data rozpoczęcia** w rekordzie **Rejestracja urlopów** |**Skorygowana data rozpoczęcia** jest wypełniana i używana podczas generowania naliczania urlopu.  |
| 509731 | Czas wolny od żądania przyszłego zakończonego pracownika powoduje problem, jeśli są one stosowane do czasu wyłączenia po dacie zakończenia zatrudnienia | Żądania wolnego czasu mogą być wysyłane dla pracowników o przyszłej dacie zakończenia zatrudnienia, o ile wniosek jest wcześniejszy niż data zakończenia zatrudnienia. |
| 510716 | Analiza wynagrodzeń obejmuje pracowników płci męskiej i żeńskiej za **Średnią stawkę za godzinę mężczyzn** | W analizie wynagrodzeń **Średnią stawkę za godzinę mężczyzn** na karcie **Analiza demograficzna wynagrodzeń** uwzględniają średnią płacę kobiet. Obejmuje tylko mężczyzn. |
| 511348 | Świadczenia samoobsługi powinny wyświetlać tylko plany świadczeń ważne od dzisiaj do końca okresu świadczenia | Wygasłe programy świadczeń zostały wyświetlone dla pracowników na stronie **Rejestracji świadczeń**. Ta poprawka usuwa te plany. |
| 512706 | Ustawienie następujących pól jako tylko do odczytu:<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | Po ukończeniu akcji przyciski **Dodawania** i **Usuwania** szczegółów wymiarów są niepoprawnie włączone. Aktualizacja strony **Szczegółów akcji dotyczących stanowisk** powoduje, że pola nie są edytowalne po wykonaniu akcji. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Human Resources w Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |
| Rozszerzone żądania i zatwierdzenia przepływu pracy | [Usprawnienia dotyczące przepływu pracy zarządzania organizacją i kadrami](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Jednostki wirtualne w Dataverse dla Human Resources | [Rozwiń dane podstawowe Dynamics 365 Human Resources w Dataverse](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Konfigurowanie jednostek wirtualnych usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Wkrótce

Następujące nowe funkcje są zaplanowane w przyszłych wydaniach:

- **Jednostki listy kontrolnej zawarte w Dataverse**: Jednostki listy kontrolnej dotyczące procesów wdrażania, odłączania, przenoszenia i obsługi procesów biznesowych będą wkrótce dostępne w Dataverse.

- **Kody przyczyn zarządzania korzyściami**: Kody przyczyn zarządzania korzyściami zostaną wkrótce połączone z istniejącymi kodami przyczyn w Human Resources. Jeśli kody przyczyn zostały utworzone w ramach zarządzania świadczeniami o długości przekraczającej 15 znaków, należy zmienić nazwę kodu przyczyny w formularzu **Kody przyczyn** na nazwę zawierającą 15 lub mniej znaków. Po zaktualizowaniu nazwy kod przyczyny pojawi się pod istniejącym formularzem w module Zarządzanie kadrami. Ta zmiana będzie dostępna w przyszłości i nie będzie miała wpływu na istniejącą funkcję.

- **Łącza niestandardowe samoobsługi Menedżera**: do menedżerów pomocy technicznej są rozszerzane funkcje samoobsługi Menedżera. Dodajemy możliwość dodawania łączy niestandardowych na karcie **Mój zespół**. Ta funkcja jest podobna do funkcji łączy niestandardowych na karcie **Moje informacje** w module samoobsługi pracownika etatowego. Aby uzyskać więcej informacji, zobacz [Niestandardowe linki w samoobsłudze menedżera](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2019 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2020, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]