---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (3 grudnia 2019 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528700"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Talent (3 grudnia 2019 r.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

W tym artykule opisano nowe oraz zmienione funkcje dostępne w Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera drobne poprawki błędów dla rozwiązania Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2646. Liczby w nawiasach w niektórych nagłówkach odnoszą się do numerów pomocy w usługach Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Obszar roboczy zarządzanie funkcjami

Obszar roboczy **zarządzanie funkcjami** zawiera listę funkcji dostarczanych w każdym wydaniu. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich. Aby uzyskać więcej informacji o zarządzaniu funkcjami funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym **zarządzanie funkcjami** można je włączyć. Niektóre funkcje mogą być domyślnie włączone.
 
Czasami funkcja jest domyślnie włączona i nie można jej wyłączyć (na przykład w obszarze roboczym **zarządzanie funkcjami**).
 
Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza **Zarządzanie funkcjami** wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Dodawanie automatycznego planowania oczyszczania historii zadań wsadowych (332528)

Dzięki tej zmianie **historia zadań wsadowych** jest uruchamiana każdej nocy i usuwa elementy historii zadań wsadowych starsze niż 30 dni.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>Aplikacja Talent nie reaguje w ramach akcji pracownika, gdy długość numeru identyfikacyjnego nie jest zgodna z typem identyfikacyjnym (390971)

To wydanie rozwiązuje problem występujący, gdy długość numeru identyfikacyjnego nie pasuje do definicji w typie identyfikacyjnym. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>Stałe wynagrodzenie nie aktualizuje poziomu przy użyciu zmian szczegółach stanowiska (348085)

W wydaniu z tego tygodnia wartość **Data początkowa wynagrodzenia** określa zadanie skojarzone ze stanowiskiem w momencie podczas tworzenia nowego rekordu stałego wynagrodzenia dla pracownika.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>Listy pracowników, pracowników etatowych i zleceniobiorców pokazują typ pracownika jako „Obydwa”, ale powinny mieć wartość tylko „Pracownik” lub „Zleceniobiorca” (384473)

Ta zmiana dokładnie odzwierciedla typ wprowadzonego pracownika (zleceniobiorca lub pracownik etatowy).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>Powiadomienia e-mail dla nowych akcji zatrudnienia nie zawierają informacji o nazwach ze względu na zasady zabezpieczeń (383402)

Ta zmiana koryguje informacje wyświetlane w polach imienia lub nazwiska w symbolach zastępczych dla przepływu pracy po włączeniu zaawansowanych zabezpieczeń.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>System pozwala na wprowadzenie dwóch wniosków o całodniowy urlop na ten sam dzień (379284)

Dzięki tej zmianie nie można wprowadzić dwóch wniosków urlopowych na ten sam dzień. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>Lista zmian adresu powinna być posortowana według daty wejścia w życie (352798)

Dzięki tej zmianie lista zmian adresu jest teraz posortowana według **daty wejścia w życie**.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>Wnioski urlopowe powinny umożliwiać usuwanie z aplikacji Common Data Service do aplikacji Talentu (376999)

Dzięki tej zmianie próbne i anulowane wnioski urlopowe mogą zostać usunięte z usługi Common Data Service, a następnie usunięte z aplikacji Talent.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>Usuwanie kodów zarobków jest dozwolone, gdy ten sam kod zarobków został przypisany do pracownika etatowego (371792)

W tej wersji należy najpierw usunąć kod zarobków z danych pracownika etatowego przed usunięciem tego kodu z systemu.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>Nie można ukończyć przepływu pracy dotyczącego urlopów i nieobecności z dwoma etapami zatwierdzania (391116)

Dzięki tej zmianie przepływ pracy dotyczący urlopów i nieobecności przechodzi przez wszystkie kroki, gdy dla wniosku skonfigurowano więcej niż jeden etap zatwierdzania.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>Data wydania nie jest synchronizowana z usługą Common Data Service po zaktualizowaniu lub wprowadzeniu w aplikacji Talent (397361)

Ta zmiana rozwiązuje problem polegający na tym, że data wystawienia rekordów typu **Identyfikacja osoby** nie została zsynchronizowana do usługi Common Data Service z aplikacji Talent.

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>Błąd odwołania cyklicznego hierarchii występuje podczas przypisywania kierownika do stanowiska (386659)

Ta zmiana koryguje unikatowy scenariusz, w którym pojawia się błąd odwołania cyklicznego podczas przypisywania nowego kierownika do stanowiska.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Jednostki usługi Common Data Service obecnie obsługujące pola niestandardowe

Pola niestandardowe są obecnie obsługiwane przez następujące jednostki usługi Common Data Service:

| Nazwisko | Jednostka |
| --- | --- |
| Wypłata na konto bankowe | cdm_bankaccountdisbursement |
| Częstotliwość obliczania świadczeń | cdm_benefitcalculationfrequency |
| Częstotliwość obliczania okresu płac dla świadczeń | cdm_benefitcalculationfrequencypayperiod |
| Stawka obliczania świadczenia | cdm_benefitcalculationrate |
| Szczegół stawki obliczania świadczenia | cdm_benefitcalculationratedetail |
| Opcja świadczenia | cdm_benefitoption |
| Plan świadczeń | cdm_benefitplan (niewłączone dla obsługi pól niestandardowych) |
| Typ świadczenia | cdm_benefittype |
| Kalendarz procesu biznesowego | cdm_businessprocesscalendar |
| Przypisanie grupy procesu biznesowego | cdm_businessprocessgroupassignment |
| Grupa zadań biblioteki procesów biznesowych | cdm_businessprocesslibrarytaskgroup |
| Etap procesu biznesowego | cdm_businessprocessstage |
| Nagłówek szablonu listy kontrolnej | cdm_businessprocesstemplateheader |
| Zadanie szablonu listy kontrolnej | cdm_businessprocesstemplatetask |
| Firma | cdm_company |
| Stały plan wynagrodzeń | cdm_compensationfixedplan |
| Siatka wynagrodzeń | cdm_compensationgrid |
| Poziom wynagrodzeń | cdm_compensationlevel |
| Wynagrodzenie — częstotliwość wypłat | cdm_compensationpayfrequency |
| Ustawianie punktów odniesienia kompensacji | cdm_compensationreferencepointsetup |
| Wiersz ustawień punktów odniesienia kompensacji | cdm_compensationreferencepointsetupline |
| Region wynagrodzenia | cdm_compensationregion |
| Struktura wynagrodzeń | cdm_compensationstructure |
| Plan wynagrodzeń o zmiennej wysokości | cdm_compensationvariableplan |
| Poziom planu wynagrodzeń o zmiennej wysokości | cdm_compensationvariableplanlevel |
| Typ planu wynagrodzeń o zmiennej wysokości | cdm_compensationvariableplantype |
| Dział | cdm_department |
| Zatrudnienie | cdm_employment |
| Pochodzenie etniczne | cdm_ethnicorigin |
| Zdarzenie dotyczące stałego wynagrodzenia | cdm_fixedcompensationevent |
| Zadanie | cdm_job |
| Czynności związane z funkcją | cdm_jobfunction |
| Stanowisko funkcji | cdm_jobposition |
| Typ funkcji | cdm_jobtype |
| Język | cdm_language |
| Transakcja banku urlopów | cdm_leavebanktransaction |
| Rejestracja urlopów | cdm_leaveenrollment |
| Plan urlopów | cdm_leaveplan |
| Wniosek urlopowy | cdm_leaverequest |
| Szczegół wniosku urlopowego | cdm_leaverequestdetail |
| Typ urlopu | cdm_leavetype |
| Kod przyczyny typu nieobecności | cdm_leavetypereasoncode |
| Cykl płac | cdm_paycycle |
| Okres kalkulacji płac | cdm_payperiod |
| Kod zarobków dla listy płac | cdm_payrollearningcode |
| Agencja wystawiająca dokument identyfikacyjny danej osoby | cdm_personidentificationissuingagency |
| Typ stanowiska | cdm_positiontype |
| Przypisanie pracownika do stanowiska | cdm_positionworkerassignmentmap |
| Kod przyczyny | cdm_reasoncode |
| Typ kwalifikacji | cdm_skilltype |
| Region podatkowy | cdm_taxregion |
| Reguła wypłat | cdm_vestingrule |
| Status kombatanta | cdm_veteranstatus |
| Kalendarz pracy | cdm_workcalendar |
| Dzień w kalendarzu roboczym | cdm_workcalendarday |
| Święto w kalendarzu pracy |cdm_workcalendarholiday |
| Wiersz dnia wolnego w kalendarzu roboczym | cdm_workcalendarholidayline |
| Zakres czasu w kalendarzu roboczym | cdm_workcalendartimeinterval (niewłączone dla obsługi pól niestandardowych) |
| Pracownik | cdm_worker |
| Adres pracownika | cdm_workeraddress |
| Konto bankowe pracownika | cdm_workerbankaccount |
| Stałe wynagrodzenia pracowników | cdm_workerfixedcompensation |
| Dane osobowe pracownika | cdm_workerpersonaldetail |
| Numer dokumentu identyfikacyjnego pracownika | cdm_workerpersonidentificationnumber |
| Typ dokumentu identyfikacyjnego pracownika | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>Wersja próbna

Funkcje w wersji zapoznawczej będą włączone tylko w środowiskach **Piaskownica**.

### <a name="print-performance-reviews"></a>Drukowanie przeglądów wydajności

Zapoznaj się z [Drukowanie przeglądów wydajności](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) w Dynamics 365: plan 2. fali publikacji 2019.


[!INCLUDE[footer-include](../includes/footer-banner.md)]