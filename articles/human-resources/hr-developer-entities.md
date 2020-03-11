---
title: Jednostki usługi Common Data Service
description: Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Common Data Service do obsługi scenariuszy rozszerzalności i integracji.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087353"
---
# <a name="common-data-service-entities"></a>Jednostki usługi Common Data Service

Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Common Data Service do obsługi scenariuszy rozszerzalności i integracji.

Aby uzyskać więcej informacji dotyczących usługi Common Data Service, zobacz temat [Co to jest usługa Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

W usłudze Common Data Service są dostępne są następujące jednostki aplikacji Human Resources.

## <a name="benefit-entities"></a>Jednostki dotyczące świadczeń

| Nazwisko | Jednostka |
| --- | --- |
| Częstotliwość obliczania świadczeń | cdm_benefitcalculationfrequency |
| Częstotliwość obliczania okresu płac dla świadczeń | cdm_benefitcalculationfrequencypayperiod |
| Stawka obliczania świadczenia | cdm_benefitcalculationrate |
| Szczegół stawki obliczania świadczenia | cdm_benefitcalculationratedetail |
| Opcja świadczenia | cdm_benefitoption |
| Plan świadczeń | cdm_benefitplan (niewłączone dla obsługi pól niestandardowych) |
| Typ świadczenia | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Jednostki zadań procesu biznesowego

| Nazwisko | Jednostka |
| --- | --- |
| Kalendarz procesu biznesowego | cdm_businessprocesscalendar |
| Przypisanie grupy procesu biznesowego | cdm_businessprocessgroupassignment |
| Grupa zadań biblioteki procesów biznesowych | cdm_businessprocesslibrarytaskgroup |
| Etap procesu biznesowego | cdm_businessprocessstage |
| Nagłówek szablonu listy kontrolnej | cdm_businessprocesstemplateheader |
| Zadanie szablonu listy kontrolnej | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Jednostki kompensacji

| Nazwisko | Jednostka |
| --- | --- |
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
| Zdarzenie dotyczące stałego wynagrodzenia | cdm_fixedcompensationevent |
| Reguła wypłat | cdm_vestingrule |
| Stałe wynagrodzenia pracowników | cdm_workerfixedcompensation |

## <a name="organization-entities"></a>Jednostki dotyczące organizacji

| Nazwisko | Jednostka |
| --- | --- |
| Dział | cdm_department |
| Zatrudnienie | cdm_employment |
| Firma | cdm_company |
| Zadanie | cdm_job |
| Czynności związane z funkcją | cdm_jobfunction |
| Stanowisko pracy | cdm_jobposition |
| Typ stanowiska | cdm_positiontype |
| Przypisanie pracownika do stanowiska | cdm_positionworkerassignmentmap |
| Typ funkcji | cdm_jobtype |
| Język | cdm_language |

## <a name="leave-and-absence-entities"></a>Jednostki dotyczące urlopów i nieobecności

| Nazwisko | Jednostka |
| --- | --- |
| Transakcja banku urlopów | cdm_leavebanktransaction |
| Rejestracja urlopów | cdm_leaveenrollment |
| Plan urlopów | cdm_leaveplan |
| Wniosek urlopowy | cdm_leaverequest |
| Szczegół wniosku urlopowego | cdm_leaverequestdetail |
| Typ urlopu | cdm_leavetype |
| Kod przyczyny typu nieobecności | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Jednostki dotyczące listy płac

| Nazwisko | Jednostka |
| --- | --- |
| Cykl płac | cdm_paycycle |
| Okres kalkulacji płac | cdm_payperiod |
| Kod zarobków dla listy płac | cdm_payrollearningcode |
| Wypłata na konto bankowe | cdm_bankaccountdisbursement |
| Region podatkowy | cdm_taxregion |

## <a name="worker-entities"></a>Jednostki dotyczące pracownika

| Nazwisko | Jednostka |
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

## <a name="worker-setup-entities"></a>Jednostki ustawień pracownika

| Nazwisko | Jednostka |
| --- | --- |
| Status kombatanta | cdm_veteranstatus |
| Pochodzenie etniczne | cdm_ethnicorigin |
| Kod przyczyny | cdm_reasoncode |
| Agencja wystawiająca dokument identyfikacyjny danej osoby | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Jednostki kwalifikacji

| Nazwisko | Jednostka |
| --- | --- |
| Typ kwalifikacji | cdm_skilltype |

## <a name="entity-relationship-models"></a>Modele relacji między jednostkami

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

[Wybieranie technologii integracji danych](hr-admin-integration-choose-technology.md)</br>
[Konfiguruj integrację z programem Common Data Service](hr-admin-integration-common-data-service.md)