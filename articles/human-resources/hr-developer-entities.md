---
title: Tabele Dataverse
description: Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Dataverse do obsługi scenariuszy rozszerzalności i integracji.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: caf8b0a5d0b24ef3619f45a6d236acae6d29c8ab
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465229"
---
# <a name="dataverse-tables"></a>Tabele Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Dataverse do obsługi scenariuszy rozszerzalności i integracji.

> [!NOTE]
> Jednostki Human Resources odpowiadają tabelom Dataverse. Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Poniższe tabele Dataverse są dostępne w oparciu o encje Human Resources.

## <a name="benefit-tables"></a>Tabele świadczeń

| Imię i nazwisko | Tabela |
| --- | --- |
| Częstotliwość obliczania świadczeń | cdm_benefitcalculationfrequency |
| Częstotliwość obliczania okresu płac dla świadczeń | cdm_benefitcalculationfrequencypayperiod |
| Stawka obliczania świadczenia | cdm_benefitcalculationrate |
| Szczegół stawki obliczania świadczenia | cdm_benefitcalculationratedetail |
| Opcja świadczenia | cdm_benefitoption |
| Plan świadczeń | cdm_benefitplan (niewłączone dla obsługi pól niestandardowych) |
| Typ świadczenia | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>Tabele zadań procesu biznesowego

| Imię i nazwisko | Tabela |
| --- | --- |
| Kalendarz procesu biznesowego | cdm_businessprocesscalendar |
| Przypisanie grupy procesu biznesowego | cdm_businessprocessgroupassignment |
| Grupa zadań biblioteki procesów biznesowych | cdm_businessprocesslibrarytaskgroup |
| Etap procesu biznesowego | cdm_businessprocessstage |
| Nagłówek szablonu listy kontrolnej | cdm_businessprocesstemplateheader |
| Zadanie szablonu listy kontrolnej | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>Tabele Wynagrodzenie

| Imię i nazwisko | Tabela |
| --- | --- |
| System stałych wynagrodzeń | cdm_compensationfixedplan |
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
| Zdarzenie dotyczące stałego wynagrodzenia | cdm_fixedcompensationevent |
| Reguła wypłat | cdm_vestingrule |
| Stałe wynagrodzenie pracownika | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>Tabele Organization

| Imię i nazwisko | Tabela |
| --- | --- |
| Dział | cdm_department |
| Zatrudnienie | cdm_employment |
| Firma | cdm_company |
| Zadanie | cdm_job |
| Czynności związane z funkcją | cdm_jobfunction |
| Stanowisko pracy | cdm_jobposition |
| Typ stanowiska | cdm_positiontype |
| Przypisanie pracownika do stanowiska | cdm_positionworkerassignmentmap |
| Wymiar stanowiska pracy | cdm_jobpositiondimension|
| Typ funkcji | cdm_jobtype |
| Język | cdm_language |
| Nazwa | cdm_title |

> [!NOTE]
> Wymiary finansowe dla **Typu stanowiska**, **Przypisania pracowników do stanowisk** i **Zatrudnienia** zapewniają integrację jednokierunkową do Dataverse. Aktualizacje wymiarów finansowych obecnie nie są synchronizowane z usługi Dataverse do Human Resources. 

## <a name="leave-and-absence-tables"></a>Tabele Urlopy i nieobecności

| Imię i nazwisko | Tabela |
| --- | --- |
| Transakcja banku urlopów | cdm_leavebanktransaction |
| Rejestracja urlopu | cdm_leaveenrollment |
| Plan urlopów | cdm_leaveplan |
| Wniosek urlopowy | cdm_leaverequest |
| Szczegół wniosku urlopowego | cdm_leaverequestdetail |
| Typ urlopu | cdm_leavetype |
| Kod przyczyny typu nieobecności | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>Tabele listy płac

| Imię i nazwisko | Tabela |
| --- | --- |
| Cykl kalkulacji płac | cdm_paycycle |
| Okres kalkulacji płac | cdm_payperiod |
| Kod zarobków dla listy płac | cdm_payrollearningcode |
| Wypłata na konto bankowe | cdm_bankaccountdisbursement |
| Region podatkowy | cdm_taxregion |

## <a name="worker-tables"></a>Tabele pracowników

| Imię i nazwisko | Tabela |
| --- | --- |
| Pracownik | cdm_worker |
| Adres pracownika | cdm_workeraddress |
| Dane osobowe pracownika | cdm_workerpersonaldetail |
| Numer dokumentu identyfikacyjnego pracownika | cdm_workerpersonidentificationnumber |
| Typ dokumentu identyfikacyjnego pracownika | cdm_workerpersonidentificationtype |
| Kalendarz pracy | cdm_workcalendar |
| Dzień w kalendarzu roboczym | cdm_workcalendarday |
| Święto w kalendarzu pracy |cdm_workcalendarholiday |
| Wiersz dnia wolnego w kalendarzu roboczym | cdm_workcalendarholidayline |
| Zakres czasu w kalendarzu roboczym | cdm_workcalendartimeinterval (niewłączone dla obsługi pól niestandardowych) |
| Konto bankowe pracownika | cdm_workerbankaccount |

## <a name="worker-setup-tables"></a>Tabele ustawień pracownika

| Imię i nazwisko | Tabela |
| --- | --- |
| Status kombatanta | cdm_veteranstatus |
| Pochodzenie etniczne | cdm_ethnicorigin |
| Kod przyczyny | cdm_reasoncode |
| Agencja wystawiająca identyfikator osoby | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Tabele kwalifikacji

| Imię i nazwisko | Tabela |
| --- | --- |
| Typ kwalifikacji | cdm_skilltype |

## <a name="table-relationship-models"></a>Tabele modeli relacji

### <a name="worker"></a>Pracownik

![Pracownik](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Stanowisko i stanowisko funkcji

![Stanowisko i stanowisko funkcji](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Świadczenia

![Świadczenia](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompensacja

![Kompensacja](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Opuść

![Opuść](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Kalendarz pracy

![Kalendarz pracy](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Informacje dodatkowe

[Wybieranie technologii integracji danych](hr-admin-integration-choose-technology.md)<br>
[Konfiguruj integrację z programem Dataverse](hr-admin-integration-common-data-service.md)<br>
[Konfiguruj tabele wirtualne usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Często zadawanych pytań dotyczące tabel wirtualnych dla Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Co to jest usługa Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Aktualizacje terminologii](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]