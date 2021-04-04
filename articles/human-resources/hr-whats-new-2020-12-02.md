---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 2 grudnia 2020 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 2 grudnia 2020 roku.
author: marcelbf
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 89c5dbab58679dfe36f5eec0d6c5724f81c18523
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463461"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources 2 grudnia 2020 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3788.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Menedżerowie mogą przesyłać wnioski o rekrutację na stanowiska | [Menedżerowie mogą przesyłać wniosek o rekrutację na dostępne stanowiska](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Dodawanie wniosku o rekrutację](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Zaawansowany profil kandydatów w zarządzaniu personelem | [Zaawansowany profil kandydatów w zarządzaniu personelem](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Dodawanie lub edytowanie profilu kandydata](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Włączanie uproszczonych integracji z dostawcami rekrutacji | [Włączanie uproszczonych integracji z dostawcami rekrutacji](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Rekrutowanie kandydatów](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |
| Łącza niestandardowe w samoobsłudze menedżera | [Łącza niestandardowe w samoobsłudze menedżera](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Łącza niestandardowe w samoobsłudze menedżera](https://aka.ms/MSSCustomLinks) |


### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie | opis |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult powinien zawierać element data/godzina, który został użyty podczas przetwarzania. | Wynik przetwarzania BenefitEligibity obejmuje obecnie sygnaturę data/godzina dla ostatniego przetwarzania, której wcześniej brakowało. |
| 526903 | Rejestracja świadczenia nie powiedzie się w przypadku planów z osobami zależnymi, gdy opcja **Automatyczny wybór osób wyznaczonych** jest włączona w opcji **Udostępniane parametry zasobów ludzkich**. | Rozwiązano błąd, w którym rejestracja świadczeń nie była możliwa dla osób pozostających na utrzymaniu, gdy włączona została opcja **Automatyczny wybór osób wyznaczonych** dla domyślnych osób wyznaczonych. |
| 521922 | Parametr **Pokaż nieobecność bez szczegółu** pokazuje szczegóły wniosków o czas wolny w kalendarzu nieobecności zespołu. | Typ urlopu, kolor typu urlopu i szczegóły dnia były wyświetlane w kalendarzu nieobecności zespołu, jeśli opcja **Pokaż nieobecność bez szczegółu** została ustawiona na **Tak** w opcji **Parametry urlopów i nieobecności**. Zostało to rozwiązane, więc teraz typ urlopu nie jest wyświetlany, a domyślny kolor typu urlopu (ciemnoniebieski) jest używany dla wszystkich typów urlopów w kalendarzu nieobecności zespołu. |
| 527316 | Zmiany tytułu dla zadania, stanowiska i powiadomień pracownika nie są synchronizowane. | Zbiór tytułu został wcześniej dodany do jednostek zadania, stanowiska i pracownika. Synchronizacja tego zbioru działa w przypadku synchronizacji modułu Human Resources z usługą Dataverse, ale nie działała w przypadku powiadomień z usługi Dataverse. Zostało to rozwiązane. |
| 512275 | Umożliwia usunięcie opcji koloru z **Parametry urlopów i nieobecności**. | Teraz, gdy kolory są zdefiniowane dla typu urlopu, opcje kolorów nie są już potrzebne w opcji **Parametry urlopów i nieobecności**, więc zostały usunięte. |
| 437112 | Mylący tekst komunikatu o błędzie podczas przypisywania stanowiska pracownika. | Zaktualizowano komunikat o błędzie podczas zatrudniania pracownika i próby przypisania pracownika do stanowiska, które nie jest aktywne. Zaktualizowano komunikat **Określone stanowisko nie jest aktywne na dzień rozpoczęcia zatrudnienia. Sprawdź czas trwania tego stanowiska.** |
| 527816 | Problemy z wydajnością na stronie **Czas wolny**. | Zwiększona wydajność na stronie **Czas wolny**. |
| 523158 | BenefitPeriodMigrationUpgrade i BenefitPlanMigrationUpgrade nie wykonują działania. | Naprawiono problemy z zadaniami migracji świadczeń związanymi z **Okresem** i **Planem**, które nie są prawidłowo wykonywane. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Human Resources w Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |
| Rozszerzone żądania i zatwierdzenia przepływu pracy | [Usprawnienia dotyczące przepływu pracy zarządzania organizacją i kadrami](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Integracja z usługą LinkedIn Talent Hub | [Integracja z usługą LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integracja z usługą LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
|Międzyfirmowe wyświetlanie urlopu dla menedżerów | [Międzyfirmowe wyświetlanie urlopu pracownika etatowego dla menedżerów](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurowanie parametrów urlopu i nieobecności](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Zapewnij dodatkowe szczegółowe informacje w saldach urlopów| [Zapewnij dodatkowe szczegółowe informacje w saldach urlopów](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Zarządzanie urlopem pracownika etatowego](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Menedżerowie mogą przesyłać wnioski o rekrutację na stanowiska | [Menedżerowie mogą przesyłać wniosek o rekrutację na dostępne stanowiska](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Dodawanie wniosku o rekrutację](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Zaawansowany profil kandydatów w zarządzaniu personelem | [Zaawansowany profil kandydatów w zarządzaniu personelem](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Dodawanie lub edytowanie profilu kandydata](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Włączanie uproszczonych integracji z dostawcami rekrutacji | [Włączanie uproszczonych integracji z dostawcami rekrutacji](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Rekrutowanie kandydatów](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Wkrótce

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2020, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]