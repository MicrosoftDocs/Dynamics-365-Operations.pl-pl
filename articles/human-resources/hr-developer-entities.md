---
title: Tabele Dataverse
description: Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Dataverse do obsługi scenariuszy rozszerzalności i integracji.
author: twheeloc
ms.date: 12/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be30f10c8e5f5e962f54f720f66c712a785835
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838590"
---
# <a name="dataverse-tables"></a>Tabele Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Moduł Microsoft Dynamics 365 Human Resources wykorzystuje usługę Dataverse do obsługi scenariuszy rozszerzalności i integracji.

> [!NOTE]
> Jednostki Human Resources odpowiadają tabelom Dataverse. Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Poniższe tabele Dataverse są dostępne w oparciu o encje Human Resources.

Więcej informacji na temat znanych problemów można znaleźć w [Szukanie problemów w Lifecycle Services (LCS)](/dev-itpro/lifecycle-services/issue-search-lcs).

## <a name="benefit-tables"></a>Tabele świadczeń

| Nazwa | Tabela | Znane problemy  | Stan |
| --- | --- |    --------|----------  |
| Częstotliwość obliczania świadczeń | cdm_benefitcalculationfrequency |     |     |
| Częstotliwość obliczania okresu płac dla świadczeń | cdm_benefitcalculationfrequencypayperiod |     |     |
| Stawka obliczania świadczenia | cdm_benefitcalculationrate |    |     |
| Szczegół stawki obliczania świadczenia | cdm_benefitcalculationratedetail |753225 | Rozstrzygnięte  |
| Opcja świadczenia | cdm_benefitoption |    |     |
| Plan świadczeń | cdm_benefitplan (niewłączone dla obsługi pól niestandardowych) |    |     |
| Typ świadczenia | cdm_benefittype |    |     |

## <a name="business-process-tasks-tables"></a>Tabele zadań procesu biznesowego

| Nazwa | Tabela |Znane problemy  | Stan |
| --- | --- |   --------|----------   |
| Kalendarz procesu biznesowego | cdm_businessprocesscalendar | 751867 | Rozstrzygnięte |
| Przypisanie grupy procesu biznesowego | cdm_businessprocessgroupassignment | 751869  751863 | Aktywni|
| Grupa zadań biblioteki procesów biznesowych | cdm_businessprocesslibrarytaskgroup |751866 | Zamknięty |
| Etap procesu biznesowego | cdm_businessprocessstage |      |     |
| Nagłówek szablonu listy kontrolnej | cdm_businessprocesstemplateheader |     |     |
| Zadanie szablonu listy kontrolnej | cdm_businessprocesstemplatetask |      |     |

## <a name="compensation-tables"></a>Tabele Wynagrodzenie

| Nazwa | Tabela |Znane problemy  | Stan |
| --- | --- | ----------      | -------    |
| System stałych wynagrodzeń | cdm_compensationfixedplan |754453 | Zamknięty |
| Siatka wynagrodzeń | cdm_compensationgrid |             |     |
| Poziom wynagrodzeń | cdm_compensationlevel |           |     |
| Wynagrodzenie — częstotliwość wypłat | cdm_compensationpayfrequency |                  |     |
| Ustawianie punktów odniesienia kompensacji | cdm_compensationreferencepointsetup |               |     |
| Wiersz ustawień punktów odniesienia kompensacji | cdm_compensationreferencepointsetupline |             |     |
| Region wynagrodzenia | cdm_compensationregion |                   |     |
| Struktura wynagrodzeń | cdm_compensationstructure |    754456        | Zamknięty    |
| Plan wynagrodzeń o zmiennej wysokości | cdm_compensationvariableplan |               |     |
| Poziom planu wynagrodzeń o zmiennej wysokości | cdm_compensationvariableplanlevel |                |     |
| Typ planu wynagrodzeń o zmiennej wysokości | cdm_compensationvariableplantype |               |     |
| Zdarzenie dotyczące stałego wynagrodzenia | cdm_fixedcompensationevent |               |     |
| Reguła wypłat | cdm_vestingrule |              |     |
| Stałe wynagrodzenie pracownika | cdm_workerfixedcompensation |              |     |

## <a name="organization-tables"></a>Tabele Organization

| Nazwa | Tabela |Znane problemy  | Stan |
| --- | --- | ----------      | -------    |
| Dział | cdm_department |  752194    | Zamknięty    |
| Zatrudnienie | cdm_employment | 762414  |  Zamknięty  |
| Firma | cdm_company |  |     |
| Funkcja | cdm_job |  |     |
| Czynności związane z funkcją | cdm_jobfunction |        |     |
| Stanowisko pracy | cdm_jobposition | 752214      | Zamknięty    |
| Typ stanowiska | cdm_positiontype |            |     |
| Przypisanie pracownika do stanowiska | cdm_positionworkerassignmentmap | 752224    |  Zamknięty   |
| Wymiar stanowiska pracy | cdm_jobpositiondimension|       |     |
| Typ funkcji | cdm_jobtype |      |     |
| Język | cdm_language |        |     |
| Nazwa | cdm_title |       |     |

> [!NOTE]
> Wymiary finansowe dla **Typu stanowiska**, **Przypisania pracowników do stanowisk** i **Zatrudnienia** zapewniają integrację jednokierunkową do Dataverse. Aktualizacje wymiarów finansowych obecnie nie są synchronizowane z usługi Dataverse do Human Resources. 

## <a name="leave-and-absence-tables"></a>Tabele Urlopy i nieobecności

| Nazwa | Tabela | Znane problemy  | Stan |
| --- | --- |   ----------      | -------    |
| Transakcja banku urlopów | cdm_leavebanktransaction |  752252    |    Rozstrzygnięte |
| Rejestracja urlopu | cdm_leaveenrollment |  752934    |Zamknięty     |
| Plan urlopów | cdm_leaveplan |   752232   |   Zamknięty  |
| Wniosek urlopowy | cdm_leaverequest | 753207     | Zamknięty    |
| Szczegół wniosku urlopowego | cdm_leaverequestdetail | 753207     |   Zamknięty  |
| Typ urlopu | cdm_leavetype |      |     |
| Kod przyczyny typu nieobecności | cdm_leavetypereasoncode |         |     |

>[!NOTE]
>Integracja z podwójnym zapisem przy użyciu tabel Dataverse dla urlopu i nieobecności jest dostępna tylko wtedy, gdy **Konfiguracja wielu typów urlopu w jednym planie urlopowym** jest włączona w Microsoft Dynamics 365 Finance przy użyciu **Zarządzanie funkcjami**. 

## <a name="payroll-tables"></a>Tabele listy płac

| Nazwa | Tabela |Znane problemy  | Stan |
| --- | --- |  ----------      | -------    |
| Cykl kalkulacji płac | cdm_paycycle |    |     |
| Okres kalkulacji płac | cdm_payperiod |          |     |
| Kod zarobków dla listy płac | cdm_payrollearningcode |   754458        |   Zamknięty  |
| Wypłata na konto bankowe | cdm_bankaccountdisbursement |    751904     |   Zamknięty  |
| Region podatkowy | cdm_taxregion |          |     |

## <a name="worker-tables"></a>Tabele pracowników

| Nazwa | Tabela |Znane problemy  | Stan |
| --- | --- |----------      | -------    |
| Pracownik | cdm_worker |    751906    |    Zamknięty |
| Adres pracownika | cdm_workeraddress |   754465     |Zamknięty     |
| Dane osobowe pracownika | cdm_workerpersonaldetail |   751906     |   Zamknięty  |
| Numer dokumentu identyfikacyjnego pracownika | cdm_workerpersonidentificationnumber |  766704      |   Zamknięty  |
| Typ dokumentu identyfikacyjnego pracownika | cdm_workerpersonidentificationtype |        |     |
| Kalendarz pracy | cdm_workcalendar |        |     |
| Dzień w kalendarzu roboczym | cdm_workcalendarday |        |     |
| Święto w kalendarzu pracy |cdm_workcalendarholiday |        |     |
| Wiersz dnia wolnego w kalendarzu roboczym | cdm_workcalendarholidayline |        |     |
| Zakres czasu w kalendarzu roboczym | cdm_workcalendartimeinterval (niewłączone dla obsługi pól niestandardowych) |        |     |
| Konto bankowe pracownika | cdm_workerbankaccount |        |     |

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

![Stanowisko i stanowisko funkcji.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Korzyści

![Korzyści.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Kompensata

![Kompensacja.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Urlop

![Urlop.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Kalendarz pracy

![Kalendarz pracy.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Informacje dodatkowe

[Wybieranie technologii integracji danych](hr-admin-integration-choose-technology.md)<br>
[Konfiguruj integrację z programem Dataverse](hr-admin-integration-common-data-service.md)<br>
[Konfiguruj tabele wirtualne usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Często zadawanych pytań dotyczące tabel wirtualnych dla Human Resources](hr-admin-virtual-entity-faq.md)<br>
[Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Aktualizacje terminologii](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
