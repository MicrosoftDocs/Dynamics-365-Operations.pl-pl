---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources w z 21 stycznia 2021 r.
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Human Resources w dniu 21 stycznia 2021 roku.
author: marcelbf
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 14df61a68ed402365bd26257cfc5e9b6b4c14db3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803376"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Human Resources w z 21 stycznia 2021 r.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano nowe, zmienione i wkrótce dostępne funkcje dostępne w rozwiązaniu Dynamics 365 Human Resources.

Aby uzyskać więcej informacji na temat procesu aktualizacji i harmonogramu, należy zapoznać się z tematem [Aktualizacja procesu](hr-admin-setup-update-process.md).

Aby uzyskać więcej informacji o nowych funkcjach i oczekiwanych ogólnych datach dostępności, zapoznaj się z [omówieniem Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>W tej wersji

Ta wersja zawiera następujące nowe funkcje i rozwiązania błędów. Zmiany dotyczą kompilacji o numerze 8.1.3866.

### <a name="new-features"></a>Nowe funkcje

W tym wydaniu są zazwyczaj dostępne następujące funkcje.

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aktualizacja Platform Update 10.0.16(40) | -- | [Aktualizacje platformy dla wersji 10.0.16 aplikacji Finance and Operations (luty 2021)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16) |
| Rozszerzone żądania i zatwierdzenia przepływu pracy | [Usprawnienia dotyczące przepływu pracy zarządzania organizacją i kadrami](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opcja konfiguracji do pozycjonowania elementów pracy na liście elementów do mnie przypisanych](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Aktualizacje przepisów ustawy ACA (ACA) dotyczące formularza 1095-C, formularza 1095-B oraz raportowania elektronicznego w starszych świadczeniach | -- | -- | 
| Zarządzanie świadczeniami teraz obsługuje raportowanie zgodności z ACA dla firm w USA | -- | [Generowanie raportów ACA w zarządzaniu świadczeniami](hr-benefits-management-aca-reports.md) |
| Zarządzanie świadczeniami jest teraz udostępniane w warstwach stawek świadczeń i stawek świadczeń drugiego poziomu  | -- | -- |

### <a name="bug-fixes"></a>Poprawki błędów

W tej wersji uwzględniono następujące poprawki błędów.

> [!NOTE]
> Naszym celem jest jak najszybsze uzyskanie tych informacji. Firma Microsoft może zaktualizować ten temat w taki sposób, aby zawierał poprawki powodujące błąd, które wprowadziły je do kompilacji po początkowym opublikowaniu tego tematu.

| Numer problemu | Wystawienie |  opis |
| --- | --- | --- |
| 533079 | Błąd nawigacji „Formularz został wywołany niepoprawnie” podczas próby wyszukiwania odliczeń. | Stały błąd podczas wyświetlania potrąceń świadczeń z wyświetlaniem **W dniu**. |
| 543641 | Kod pocztowy nie jest wypełniany w raportach elektronicznych.  | Naprawiono błąd wewnętrzny w kodzie pocztowym, który nie pojawiał się w raportach elektronicznych ACA do zarządzania świadczeniami, gdy kod zakresu to M do Q. |
| 542815 | Osobisty ekran osoby kontaktowej w formularzu Samoobsługa pracownika umożliwia pracownikom wyświetlanie kontaktów osobistych innych osób. | Stały błąd, w którym formularz **Edycji** samoobsługowych kontaktów osobistych pracownika nie ogranicza jego kwerendy na tyle, aby zagwarantować pobranie tylko jednego kontaktu osobistego, umożliwiając użytkownikowi korzystanie ze skrótów klawiaturowych do wyświetlania kontaktów innych osób. |
| 536157 | Nie można otworzyć strony **integracji Microsoft Dataverse** w administrowaniu systemem z powodu wywołania IsVirtualEntityPackageInstalled(). | Problem uniemożliwia ładowanie strony **integracji Microsoft Dataverse** w Human Resources. |
| 533079 | Błąd nawigacji „Formularz został wywołany niepoprawnie” podczas próby wyszukiwania odliczeń. | Stały błąd podczas wyświetlania w formularzu **Odliczenia** na podstawie świadczeń w widoku **Do dnia**. |
| 537264 | Na skróconej karcie **Informacji osobistych** w rekordzie kandydata. | Dane osobowe kandydata są teraz dostępne w rekordzie kandydata. |
| 537267 | **Doświadczenie zawodowe** nie jest wyświetlane w wewnętrznych rekordach kandydatów. | Skrócone karty **Doświadczenie zawodowe** są wyświetlane w wewnętrznych rekordach kandydatów. Wcześniej, jeśli kandydat był wewnętrzny, **Doświadczenie zawodowe** zostało zastąpione **Historią zatrudnienia**, która jest historią zatrudnienia kandydata w organizacji. Obie te informacje mają zastosowanie i muszą być wyświetlane dla kandydatów wewnętrznych. |
| 537067 | **Możliwość kontaktowania się z pracodawcą** nie jest wyświetlana. | Kontolka **Możliwy kontakt z pracodawcą** został dodany do okienka **Edytowanie doświadczenia zawodowego** dla rekordu kandydata. |
| 525957 | Po zakończeniu przenoszenia **Stan kandydata** nie jest zmieniany dla wewnętrznych kandydatów. | Po zakończeniu przenoszenia (po wybraniu przycisku **Zmień stanowisko** lub **Kontynuuj** na stronie **Przenoszenia pracownika do nowego przypisania stanowiska**) **Stan** w rekordzie kandydata musi ulec zmianie na **Zatrudniony**. |
| 537051 | Symbole waluty rupia indyjska i lira tureckie nie są poprawnie synchronizowane z Dataverse | Symbole rupii indyjskiej i liry tureckiej są teraz poprawnie synchronizowane z Dataverse. |
| 534846 | Tabele rekrutacji muszą być włączone dla zarządzania danymi. | Nowe tabele utworzone dla żądań rekrutacyjnych i kandydatów są teraz włączone do zarządzania danymi. Umożliwia to włączenie śledzenia zmian dla tabel, umożliwiając śledzenie zmian OData w wirtualnych tabelach Dataverse. |
| 533474 | Popraw brakujące odwołanie do pliku Microsoft.SqlServer.XEvent.dll. | Wyjątki dotyczące ładowania zestawu dla biblioteki Microsoft.SqlServer.XEvent.dll blokowały tabele wirtualne Dataverse przed skonfigurowaniem w niektórych środowiskach. |
| 481122 | Obszar roboczy **Osoby** pokazujące wycofane stanowiska. | Wycofane stanowiska były wyświetlane jako otwarte stanowiska w obszarze roboczym **Osoby**. Wycofane stanowiska nie są już wyświetlane. | 
| 541978 | Dodaj podstawowy adres e-mail do jednostki BaseWorker. | Ta zmiana dodała podstawowy adres e-mail pracownika do hcmWorkerBaseEntity. |

## <a name="in-preview"></a>Wersja próbna

Następujące nowe funkcje są dostępne w wersji zapoznawczej. Aby uzyskać informacje na temat włączania lub włączania funkcji w wersji zapoznawczej, zobacz [Zarządzanie funkcjami](hr-admin-manage-features.md).

| Funkcja | Plan wydań | Dokumentacja |
| --- | --- | --- |
| Aplikacja Human Resources w Microsoft Teams | [Urlop pracownika etatowego i nieobecność pracowników w Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplikacja Human Resources w Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Zarządzanie wnioskami o urlop w Teams](hr-teams-leave-app.md) |
| Integracja z usługą LinkedIn Talent Hub | [Integracja z usługą LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integracja z usługą LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Międzyfirmowe wyświetlanie urlopu dla menedżerów | [Międzyfirmowe wyświetlanie urlopu pracownika etatowego dla menedżerów](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Konfigurowanie parametrów urlopu i nieobecności](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Zapewnij dodatkowe szczegółowe informacje w saldach urlopów| [Zapewnij dodatkowe szczegółowe informacje w saldach urlopów](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Zarządzanie urlopem pracownika etatowego](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Menedżerowie mogą przesyłać wnioski o rekrutację na stanowiska | [Menedżerowie mogą przesyłać wniosek o rekrutację na dostępne stanowiska](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Dodawanie wniosku o rekrutację](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Zaawansowany profil kandydatów w zarządzaniu personelem | [Zaawansowany profil kandydatów w zarządzaniu personelem](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Dodawanie lub edytowanie profilu kandydata](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Włączanie uproszczonych integracji z dostawcami rekrutacji | [Włączanie uproszczonych integracji z dostawcami rekrutacji](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Rekrutowanie kandydatów](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Wkrótce
| Funkcja | Szczegóły |
| --- | --- |
| Potwierdzenie e-mail dla zapisów na świadczenia | Ta funkcja zapewni opcję wysyłania wiadomości e-mail z potwierdzeniem do pracowników, gdy wymeldują się z doświadczeń związanych z rejestracją świadczeń w ramach samoobsługi pracowników. Aby zobaczyć więcej informacji, zobacz [Konfigurowanie parametrów zarządzania świadczeniami w firmie](hr-benefits-setup-parameters-per-company.md). |
| Umiejętności wprowadzone przez menedżera dla swoich pracowników mogą być automatycznie zatwierdzane w przepływie pracy | Wkrótce. |

Aby uzyskać pełną listę zaplanowanych funkcji i ich zaplanowanych wersji, zajrzyj do [omówienia Dynamics 365 Human Resources 2020 wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Aktualizacje terminologii dla Microsoft Dataverse

Od 2020 listopada Common Data Service zmieniło nazwę na [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Więcej informacji można znaleźć w [oficjalnym oświadczeniu](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) na stronie bloga Power Apps. W połączeniu ze zmianą tej nazwy niektóre terminologii Dataverse zostały zaktualizowane. Na przykład *jednostka* to teraz *tabela*, a *pole* to teraz *kolumna*. Aby uzyskać więcej informacji, zobacz [Aktualizacje terminologii](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

W tej wersji terminologia związana z integracją Dynamics 365 Human Resources z Dataverse została zaktualizowana w całej aplikacji, aby odzwierciedlić te zmiany. Na przykład formularz **integracji Common Data Service** jest teraz **integracją Microsoft Dataverse**.

Aby dowiedzieć się więcej o integracji Dynamics 365 Human Resources z programem Microsoft Dataverse, zobacz temat [Konfigurowanie integracji Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) i [Konfigurowanie tabel wirtualnych Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="see-also"></a>Informacje dodatkowe

[Nowości i zmiany w rozwiązaniu Human Resources](hr-admin-whats-new.md)</br>
[Omówienie rozwiązania Dynamics 365 Human Resources 2020, wydanie 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)</br>
[Zarządzanie funkcjami](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]