---
title: Konfiguracja integracji z tabelami dataverse
description: W tym artykule opisano integrację między Microsoft Dynamics 365 Human Resources i Dataverse.
author: anschmidt
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63c25020b7026a76ecc6e2c3563f8299627ec8a8
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838630"
---
# <a name="configure-integration-with-dataverse-tables"></a>Konfiguracja integracji z tabelami Dataverse

>[!Important]
>Funkcjonalność opisana w tym artykule jest obecnie dostępna dla klientów Dynamics 365 Human Resources na infrastrukturze aplikacji finansowych i operacyjnych. 


Aby zintegrować Microsoft Dynamics 365 Human Resources z Dataverse, można użyć [Integratora danych](/powerapps/administrator/data-integrator). Szablon Human Resources-do-Dataverse umożliwia przepływ danych dotyczących zawodów, stanowisk, pracowników i innych z Human Resources do Dataverse oraz z Dataverse do Human Resources, tworząc zapis w obu systemach.

## <a name="system-requirements-for-human-resources"></a>Wymagania systemowe modułu Human Resources

Rozwiązanie integracyjne wymaga następujących wersji modułu Human Resources i aplikacji Dynamics 365 Finance: 

- Dynamics 365 Finance w wersji 7.2 lub nowszej
- Środowisko Dynamics CRM, w którym została utworzona baza danych i dozwolone są aplikacje Dynamics 365

## <a name="template-and-tasks"></a>Szablon i zadania

Wykonaj poniższe kroki, aby uzyskać dostęp do szablonu Zasoby ludzkie do Finance.

1. Otwórz [centrum administracyjne Power Apps](https://admin.powerapps.com/). 
2. W swoim środowisku wybierz **Aplikacje Dynamics 365 Apps**, a następnie wybierz **Źródło aplikacji** na pasku narzędzi.
3. Aby zainstalować szablon, wyszukaj hasło „Podwójny zapis Zasoby ludzkie” lub przejdź bezpośrednio pod następujący adres: <https://appsource.microsoft.com/product/dynamics-365/mscrm.hcm_dualwrite>.
3. Po zakończeniu instalacji otwórz Dynamics 365 Finance.
4. Otwórz obszar roboczy **Zarządzanie danymi**. 
5. Wybierz **Podwójny zapis**. 
6. Wykonaj proces łączenia środowiska dla co najmniej jednej firmy w organizacji. 
7. Po zakończeniu tworzenia połączenia ze środowiskiem Dataverse wybierz **Zastosuj rozwiązanie**. Rozwiązanie jest stosowane, a mapowania są instalowane w aplikacji integratora.

## <a name="template-mappings"></a>Mapowania w szablonie

W poniższych tabelach mapowania szablonów nazwa zadania wskazuje na encje, które są używane w każdej aplikacji. Finanse są po lewej stronie, a Dataverse po prawej.

### <a name="bank-account-disbursements-dual-write-to-bank-account-disbursement"></a>Wypłaty z rachunku bankowego (podwójny zapis) do Wypłaty z rachunku bankowego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATIONID        | cdm\_bankaccountid.cdm\_accountidentification        |
| AMOUNT                         | cdm\_amount                                         |
| PRIORITY                       | cdm\_disbursementpriority                           |
| PERSONNELNUMBER                | cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber    |
| REMAINDER                      | cdm\_isremainder                                    |

### <a name="benefit-calculation-rate-detail-dual-write-to-benefit-calculation-rate-detail"></a>Szczegóły dotyczące stawki obliczania świadczenia (podwójny zapis) do Szczegóły dotyczące stawki obliczania świadczenia

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CONTRIBUTIONMETHOD             | cdm\_contributionmethod                             |
| EFFECTIVE                      | cdm\_effective                                      |
| EMPLOYERCONTRIBUTION           | cdm\_employercontribution                           |
| EXPIRATION                     | cdm\_expiration                                     |
| WORKERDEDUCTION                | cdm\_workerdeduction                                |
| NAME                           | cdm\_calculationrateid.cdm\_name                     |

### <a name="benefit-calculation-rate-header-to-benefit-calculation-rate"></a>Stopa wyliczania nagłówka świadczenia do Stopy wyliczania świadczenia

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| NAME                           | cdm\_name                                           |
| TIERTYPE                       | cdm\_tiertype                                       |

### <a name="benefit-option-to-benefit-option"></a>Opcja świadczenia do Opcja świadczenia

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ALLOWBENEFICIARYDESIGNATIONS   | cdm\_allowbeneficiarydesignations                   |
| ALLOWDEPENDENTCOVERAGE         | cdm\_allowdependentcoverage                         |
| BENEFITOPTIONID                | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISWAIVE                        | cdm\_iswaived                                       |

### <a name="benefit-type-to-benefit-type"></a>Typ świadczenia do typu świadczenia

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| BENEFITTYPEID                  | cdm\_name                                           |
| CONCURRENTENROLLMENT           | cdm\_concurrentenrollment                           |
| DESCRIPTION                    | cdm\_description                                    |
| PAYROLLCATEGORY                | cdm\_payrollcategory                                |

### <a name="business-calendar-to-business-process-calendar"></a>Kalendarz biznesowy do kalendarza procesów biznesowych

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NAME                           | cdm\_calendarname                                   |
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| ISOPENMONDAY                   | cdm\_ismondayopen                                   |
| ISOPENTUESDAY                  | cdm\_istuesdayopen                                  |
| ISOPENWEDNESDAY                | cdm\_iswednesdayopen                                |
| ISOPENTHURSDAY                 | cdm\_isthursdayopen                                 |
| ISOPENFRIDAY                   | cdm\_isfridayopen                                   |
| ISOPENSATURDAY                 | cdm\_issaturdayopen                                 |
| ISOPENSUNDAY                   | cdm\_issundayopen                                   |

### <a name="business-process-to-business-process-header"></a>Proces biznesowy do Nagłówka procesu biznesowego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processid                                      |
| PROCESSTYPE                    | cdm\_processtype                                    |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| STATUS                         | cdm\_status                                         |
| TARGETDATE                     | cdm\_targetdate                                     |
| STARTDATETIME                  | cdm\_startdatetime                                  |
| ENDDATETIME                    | cdm\_enddatetime                                    |
| RESOLVEDBYPERSONNELNUMBER      | cdm\_resolvedbyid.cdm\_workernumber                  |
| PROCESSOWNERPERSONNELNUMBER    | cdm\_processownerid.cdm\_workernumber                |
| SOURCETEMPLATENAME             | cdm\_sourcetemplateid.cdm\_name                      |
| SOURCETEMPLATEPROCESSTYPE      | cdm\_sourcetemplateid.cdm\_businessprocesstype       |
| SOURCETEMPLATEGENERICSUBTYPE   | cdm\_sourcetemplateid.cdm\_genericsubtype            |

### <a name="business-process-library-task-group-to-business-process-library-task-group"></a>Grupa zadań biblioteki procesów biznesowych do Grupy zadań biblioteki procesów biznesowych

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_processtype                                    |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="business-process-stage-to-business-process-stage"></a>Etap procesu biznesowego do etapu procesu biznesowego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| SEQUENCENUMBER                 | cdm\_sequencenumber                                 |

### <a name="business-process-task-to-business-process-task"></a>Zadanie procesu biznesowego do zadania procesu biznesowego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| DUEDATE                        | cdm\_duedate                                        |
| TASKID                         | cdm\_taskid                                         |
| INSTRUCTIONS                   | cdm\_instructions                                   |
| COMPLETIONDATETIME             | cdm\_completiondatetime                             |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| NAME                           | cdm\_name                                           |
| STATUS                         | cdm\_status                                         |
| RESOLVEDBY\_PERSONNELNUMBER     | cdm\_resolvedbyid.cdm\_workernumber                  |
| TEMPLATETASKID                 | cdm\_templatetaskid.cdm\_taskid                      |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedposition.cdm\_jobpositionnumber         |

### <a name="business-process-template-to-checklist-template-header"></a>Szablon procesu biznesowego do Nagłówka szablonu listy kontrolnej

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| CALENDARID                     | cdm\_businessprocesscalendarid.cdm\_name             |
| PERSONNELNUMBER                | cdm\_processownerid.cdm\_workernumber                |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="business-process-template-task-to-checklist-template-task"></a>Zadanie szablonu procesu biznesowego do zadania szablonu listy kontrolnej

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TASKID                         | cdm\_taskid                                         |
| NAME                           | cdm\_name                                           |
| TEMPLATEHEADER\_PROCESSTYPE     | cdm\_businessprocesstemplateheaderid.cdm\_businessprocesstype |
| TEMPLATEHEADER\_GENERICSUBTYPE  | cdm\_businessprocesstemplateheaderid.cdm\_genericsubtype |
| TEMPLATEHEADER\_NAME            | cdm\_businessprocesstemplateheaderid.cdm\_name       |
| DESCRIPTION                    | cdm\_description                                    |
| DUEDATEOFFSETDAYS              | cdm\_duedateoffsetdays                              |
| MENUITEMTYPE                   | cdm\_tasklinktype                                   |
| MENUITEM                       | cdm\_tasklink                                       |
| CONTACTPERSON\_PERSONNELNUMBER  | cdm\_contactpersonid.cdm\_workernumber               |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedpositionid.cdm\_jobpositionnumber       |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| INSTRUCTIONS                   | cdm\_instructions                                   |

### <a name="calculation-frequency-to-benefit-calculation-frequency"></a>Częstotliwość obliczania do Częstotliwość obliczania świadczeń

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| FREQUENCY                      | cdm\_name                                           |
| FREQUENCYCONTROL               | cdm\_frequencycontrol                               |
| ISIMMUTABLE                    | cdm\_isimmutable                                    |

### <a name="calculation-frequency-pay-period-to-benefit-calculation-frequency-pay-period"></a>Częstotliwość obliczania okresu rozliczeniowego do Częstotliwości obliczania okresu rozliczeniowego świadczenia

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALCULATIONFREQUENCYID         | cdm\_benefitcalculationfrequencyid.cdm\_name         |
| PERIODSTARTDATE                | cdm\_payperiodid.cdm\_periodstartdate                |
| PAYCYCLEID                     | cdm\_payperiodid.cdm\_paycycleid.cdm\_name            |

### <a name="calendar-to-work-calendar"></a>Kalendarz do Kalendarza roboczego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| CALENDARNAME                   | cdm\_description                                    |
| WORKCALENDARHOLIDAYID          | cdm\_workcalendarholidayid.cdm\_name                 |

### <a name="compensation-fixed-action-table-to-fixed-compensation-event"></a>Tabela stałych działań kompensacyjnych do Stałego zdarzenia kompensacyjnego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACTION                         | cdm\_name                                           |
| ACTIVE                         | cdm\_isactive                                       |
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_eventtype                                      |

### <a name="compensation-fixed-plan-to-compensation-fixed-plan"></a>Stały plan kompensacyjny do stałego planu kompensacyjnego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PLAN                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_type                                           |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| CURRENCY                       | cdm\_transactioncurrencyid.isocurrencycode          |
| PAYFREQUENCY                   | cdm\_payfrequency.cdm\_name                          |
| HIRERULE                       | cdm\_hirerule                                       |
| OUTOFRANGETOLERANCE            | cdm\_outofrangetolerance                            |
| RECOMMENDATIONALLOWED          | cdm\_recommendationallowed                          |
| COMPENSATIONSTRUCTURE          | cdm\_compensationgrid.cdm\_name                      |
| REFPOINTSETUPID                | cdm\_referencepointsetupline.cdm\_referencepointsetupid.cdm\_name |
| CONTROLPOINT                   | cdm\_referencepointsetupline.cdm\_name               |

### <a name="compensation-grids-to-compensation-grid"></a>Siatki wynagrodzeń do Siatki wynagrodzeń

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| GRIDID                         | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| REFERENCESETUP                 | cdm\_referencepointsetupid.cdm\_name                 |
| TYPE                           | cdm\_type                                           |
| CURRENCY                       | cdm\_transactioncurrencyid.isocurrencycode          |

### <a name="compensation-job-function-to-job-function"></a>Funkcja kompensacji do funkcji pracy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBFUNCTIONID                  | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="compensation-job-type-to-job-type"></a>Wyrównanie typu pracy do typu pracy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBTYPEID                      | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| EXEMPTSTATUS                   | cdm\_exemptstatus                                   |

### <a name="compensation-pay-frequency-to-compensation-pay-frequency"></a>Częstotliwość płacenia kompensacji do Częstotliwość płacenia kompensacji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYRATECONVERSION              | cdm\_name                                           |
| PERIOD                         | cdm\_period                                         |
| DESCRIPTION                    | cdm\_description                                    |
| ANNUALCONVERSIONFACTOR         | cdm\_annualconversionfactor                         |
| HOURLYCONVERSIONFACTOR         | cdm\_hourlyconversionfactor                         |
| MONTHLYCONVERSIONFACTOR        | cdm\_monthlyconversionfactor                        |
| WEEKLYCONVERSIONFACTOR         | cdm\_weeklyconversionfactor                         |

### <a name="compensation-regions-to-compensation-region"></a>Regiony kompensacyjne do Regionu kompensacyjnego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| LOCATION                       | cdm\_name                                           |

### <a name="compensation-variable-plan-v2-to-compensation-variable-plan"></a>Zmienny plan kompensacyjny V2 do Zmiennego planu kompensacyjnego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VARIABLEAWARDBASIS             | cdm\_awardbasis                                     |
| AWARDBASISCALCULATION          | cdm\_awardbasiscalculation                          |
| CALCULATIONTYPE                | cdm\_calculationtype                                |
| DESCRIPTION                    | cdm\_description                                    |
| ENABLEENROLLMENT               | cdm\_enableenrollment                               |
| ENABLELEVELS                   | cdm\_enablelevels                                   |
| ENABLERECOMMENDATION           | cdm\_enablerecommendation                           |
| HIRERULE                       | cdm\_hirerule                                       |
| LEVERAGE100PERCENT             | cdm\_leverage100percent                             |
| LEVERAGEMAXIMUM                | cdm\_leveragemaximum                                |
| LEVERAGEMINIMUM                | cdm\_leverageminimum                                |
| LEVERAGEOVEROBJECTIVE          | cdm\_leverageoverobjective                          |
| LEVERAGEUNDEROBJECTIVE         | cdm\_leverageunderobjective                         |
| PERCENTOFBASIS                 | cdm\_percentofbasis                                 |
| PLANID                         | cdm\_name                                           |
| VARIABLECOMPENSATIONTYPE       | cdm\_variablecompensationtypeid.cdm\_name            |
| UNITCURRENCYCODE               | transactioncurrencyid.isocurrencycode              |
| UNITRELATIONSHIP               | cdm\_unitrelationship                               |
| UNITVALUE                      | cdm\_unitvalue                                      |
| NUMBEROFUNITSREAL              | cdm\_numberofunits                                  |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VESTINGRULE                    | cdm\_vestingruleid.cdm\_name                         |
| LEVERAGETOLERANCEMAX           | cdm\_leveragetolerancemax                           |
| LEVERAGETOLERANCEMIN           | cdm\_leveragetolerancemin                           |

### <a name="compensation-variable-type-to-compensation-variable-plan-type"></a>Typ zmiennej kompensacyjnej do Typu planu zmiennej kompensacyjnej

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_awardtype                                      |
| VARIABLECOMPENSATIONTYPE       | cdm\_name                                           |

### <a name="compensation-vesting-rules-to-vesting-rule"></a>Zasady nabywania uprawnień do świadczeń kompensacyjnych do Zasady nabywania uprawnień

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| NOTE                           | cdm\_notes                                          |
| VESTINGRULE                    | cdm\_name                                           |

### <a name="department-v2-to-department"></a>Dział V2 do Działu

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| OPERATINGUNITNUMBER            | cdm\_departmentnumber                               |
| NAME                           | cdm\_name                                           |
| SEARCHNAME                     | cdm\_description                                    |
| PARTYTYPE                      | cdm\_partytype                                      |

### <a name="dual-write-tax-region-to-tax-region"></a>Podwójny zapis regionu podatkowego do regionu podatkowego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CITY                           | cdm\_city                                           |
| COUNTRYORREGION                | cdm\_countryorregion                                |
| COUNTY                         | cdm\_county                                         |
| STATE                          | cdm\_stateorprovince                                |
| TAXREGIONNAME                  | cdm\_name                                           |

### <a name="dual-write-worker-identification-to-worker-person-identification-number"></a>Podwójny zapis Numeru Identyfikacyjnego Pracownika do Numeru Identyfikacyjnego Osoby Pracownika

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| ENTRYTYPE                      | cdm\_entrytype                                      |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| IDENTIFICATIONNUMBER           | cdm\_identificationnumber                           |
| IDENTIFICATIONTYPEID           | cdm\_identificationtypeid.cdm\_name                  |
| ISPRIMARY                      | cdm\_isprimary                                      |
| ISSUEDATE                      | cdm\_issuedate                                      |
| ISSUINGAGENCYID                | cdm\_issuingagencyid.cdm\_name                       |
| WORKERNUMBER                   | cdm\_workerid.cdm\_workernumber                      |

### <a name="compensation-structure-to-compensation-structure"></a>Struktura kompensacji do Struktura kompensacji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AMOUNT                         | cdm\_amount                                         |
| GRID                           | cdm\_compensationgridid.cdm\_name                    |
| LEVELID                        | cdm\_compensationlevelid.cdm\_name                   |
| REFERENCEPOINTLINENUMBER       | cdm\_referencepointid.cdm\_linenumber                |
| REFERENCESETUP                 | cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name |
| REFERENCEPOINT                 | cdm\_referencepointid.cdm\_name                      |

### <a name="earning-code-to-payroll-earning-code"></a>Kod zarobków do listy płac Kod zarobków

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EARNINGCODE                    | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| INCLUDEINPAYMENTTYPE           | cdm\_includeinpaymenttype                           |
| QUANTITYUNIT                   | cdm\_quantityunit                                   |
| TRACKFMLAHOURS                 | cdm\_trackfmlahours                                 |
| ISPRODUCTIVE                   | cdm\_isproductive                                   |

### <a name="employee-fixed-compensation-to-worker-fixed-compensation"></a>Stałe wynagrodzenie pracownika do stałego wynagrodzenia pracownika

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| TYPE                           | cdm\_compensationtype                               |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| LINENUMBER                     | cdm\_linenumber                                     |
| PAYFREQUENCY                   | cdm\_payfrequencyid.cdm\_name                        |
| PAYRATE                        | cdm\_payrate                                        |
| PLAN                           | cdm\_planid.cdm\_name                                |
| POSITIONID                     | cdm\_positionid.cdm\_jobpositionnumber               |
| PROCESSTYPE                    | cdm\_processtype                                    |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| ACTION                         | cdm\_eventid.cdm\_name                               |
| STEP                           | cdm\_referencepointsetuplineid.cdm\_name             |
| REFPOINTSETUPID                | cdm\_referencepointsetuplineid.cdm\_referencepointsetupid.cdm\_name |

### <a name="employment-per-company-to-employment"></a>Zatrudnienie na firmę do Zatrudnienie

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EMPLOYMENTENDDATE              | cdm\_employmentenddate                              |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| EMPLOYMENTSTARTDATE            | cdm\_employmentstartdate                            |
| WORKERTYPE                     | cdm\_workertype                                     |
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| ADJUSTEDWORKERSTARTDATE        | cdm\_adjustedworkerstartdate                        |
| EMPLOYERNOTICEAMOUNT           | cdm\_employernoticeamount                           |
| EMPLOYERUNITOFNOTICE           | cdm\_employerunitofnotice                           |
| WORKERUNITOFNOTICE             | cdm\_workerunitofnotice                             |
| WORKERNOTICEAMOUNT             | cdm\_workernoticeamount                             |
| LASTDATEWORKED                 | cdm\_lastdateworked                                 |
| PROBATIONENDDATE               | cdm\_probationenddate                               |
| TRANSITIONDATE                 | cdm\_transitiondate                                 |
| TRANSITIONREASONCODENAME       | cdm\_transitionreasoncode.cdm\_name                  |
| WORKERSTARTDATE                | cdm\_workerstartdate                                |
| VALIDTO                        | cdm\_validto                                        |
| VALIDFROM                      | cdm\_validfrom                                      |

### <a name="ethnic-origins-to-ethnic-origin"></a>Pochodzenie etniczne do Pochodzenie etniczne

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ETHNICORIGINID                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="group-assignment-to-business-process-group-assignment"></a>Przypisanie grupy do procesu biznesowego Przypisanie grupy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="identification-type-to-worker-person-identification-type"></a>Typ identyfikacyjny dla pracownika Typ identyfikacyjny osoby

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| IDENTIFICATIONTYPEID           | cdm\_name                                           |
| ALLOWEDVALUES                  | cdm\_allowedvalues                                  |
| FIXEDLENGTH                    | cdm\_fixedlength                                    |
| IDENTIFICATIONNUMBERFORMAT     | cdm\_identificationnumberformat                     |

### <a name="issuing-agency-to-person-identification-issuing-agency"></a>Agencja wydająca do Agencji Wydającej Identyfikację Osoby

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EMAIL                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| ISSUINGAGENCY                  | cdm\_name                                           |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| NAME                           | cdm\_description                                    |
| PAGER                          | cdm\_pager                                          |
| SMS                            | cdm\_sms                                            |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telex                                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |

### <a name="job-positions-dual-write-to-job-position"></a>Podwójny zapis pozycji pracy do pozycji pracy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONID                     | cdm\_jobpositionnumber                              |
| ACTIVATION                     | cdm\_activation                                     |
| AVAILABLEFORASSIGNMENT         | cdm\_availableforassignment                         |
| COMPENSATIONREGIONID           | cdm\_compensationregionid.cdm\_name                  |
| DEPARTMENTID                   | cdm\_departmentid.cdm\_departmentnumber              |
| DESCRIPTION                    | cdm\_description                                    |
| FULLTIMEEQUIVALENT             | cdm\_fulltimeequivalent                             |
| JOBID                          | cdm\_jobid.cdm\_name                                 |
| PARENTPOSITIONID               | cdm\_parentjobpositionid.cdm\_jobpositionnumber      |
| POSITIONTYPEID                 | cdm\_positiontypeid.cdm\_name                        |
| RETIREMENT                     | cdm\_retirement                                     |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |

### <a name="jobs-dual-write-to-job"></a>Podwójny zapis pracy do zadania

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBID                          | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| JOBDESCRIPTION                 | cdm\_jobdescription                                 |
| ALLOWUNLIMITEDPOSITIONS        | cdm\_allowunlimitedpositions                        |
| MAXIMUMNUMBEROFPOSITIONS       | cdm\_maximumnumberofpositions                       |
| JOBFUNCTIONID                  | cdm\_jobfunctionid.cdm\_name                         |
| JOBTYPEID                      | cdm\_jobtypeid.cdm\_name                             |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| DEFAULTFULLTIMEEQUIVALENCY     | cdm\_defaultfulltimeequivalent                      |

### <a name="language-codes-to-language"></a>Kody językowe do Język

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LANGUAGECODEID                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="leave-and-absence-bank-transaction-v2-to-leave-bank-transaction"></a>Transakcja bankowa dotycząca urlopu i nieobecności V2 do Transakcja bankowa dotycząca urlopu

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AMOUNT                         | cdm\_amount                                         |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TRANSACTIONDATE                | cdm\_transactiondate                                |
| TRANSACTIONNUMBER              | cdm\_transactionnumber                              |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| TRANSACTIONTYPE                | cdm\_transactiontype                                |

### <a name="leave-and-absence-enrollment-v2-to-leave-enrollment"></a>Zapisywanie na urlopy i nieobecności V2 do Zapisywanie na urlopy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| CUSTOMDATE                     | cdm\_customdate                                     |
| ACCRUALSTARTDATE               | cdm\_accrualstartdate                               |
| ACCRUALDATEBASIS               | cdm\_accrualdatebasis                               |
| ISACCRUALSUSPENDED             | cdm\_isaccrualsuspended                             |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TIERBASIS                      | cdm\_tierbasis                                      |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |

### <a name="leave-and-absence-plan-v2-to-leave-plan"></a>Plan urlopów i nieobecności V2 do Planu urlopów

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCRUALFREQUENCY               | cdm\_accrualfrequency                               |
| NAME                           | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| STARTDATE                      | cdm\_startdate                                      |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-and-absence-type-to-leave-type"></a>Typ urlopu i nieobecności na Typ urlopu

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_type                                           |
| EARNINGCODEID                  | cdm\_earningcodeid.cdm\_name                         |

### <a name="leave-and-absence-type-reason-code-to-leave-type-reason-code"></a>Kod powodu typu urlopu i nieobecności na Kod powodu typu urlopu

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LEAVETYPE                      | cdm\_typeid.cdm\_type                                |
| REASONCODEID                   | cdm\_reasoncodeid.cdm\_name                          |

### <a name="leave-time-off-request-detail-to-leave-request-detail"></a>Szczegóły wniosku o urlop do Szczegóły wniosku o urlop

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AMOUNT                         | cdm\_amount                                         |
| LEAVEDATE                      | cdm\_leavedate                                      |
| REQUESTID                      | cdm\_leaverequestid.cdm\_leaverequestnumber          |
| TYPE                           | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-time-off-request-header-to-leave-request"></a>Nagłówek wniosku o urlop do wniosku o urlop

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REQUESTID                      | cdm\_leaverequestnumber                             |
| REQUESTDATE                    | cdm\_requestdate                                    |
| STATUS                         | cdm\_status                                         |
| COMMENT                        | cdm\_comment                                        |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |

### <a name="levels-to-compensation-level"></a>Poziomy do poziomu kompensacji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TYPE                           | cdm\_type                                           |
| DESCRIPTION                    | cdm\_description                                    |
| LEVEL                          | cdm\_name                                           |

### <a name="onboarding-process-header-to-onboard-process-header"></a>Nagłówek procesu onboardingu do Nagłówek procesu onboardingu

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ONBOARDEDEMPLOYEEPERSONNELNUMBER | cdm\_onboardedemployeeid.cdm\_workernumber           |
| EMPLOYMENTPERSONNELNUMBER      | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| LEGALENTITYID                  | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |
| EMPLOYMENTSTARTDATE            | cdm\_employmentid.cdm\_employmentstartdate           |

### <a name="pay-cycle-to-pay-cycle"></a>Cykl płac do cyklu płac

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| PAYCYCLEFREQUENCY              | cdm\_frequency                                      |

### <a name="pay-period-to-pay-period"></a>Okres płac do okresu płac

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMMENTS                       | cdm\_description                                    |
| DEFAULTPAYMENTDATE             | cdm\_defaultpaymentdate                             |
| PAYCYCLEID                     | cdm\_paycycleid.cdm\_name                            |
| PERIODENDDATE                  | cdm\_periodenddate                                  |
| PERIODSTARTDATE                | cdm\_periodstartdate                                |
| STATUS                         | cdm\_status                                         |

### <a name="payroll-details-for-positions-to-payroll-position-detail"></a>Szczegóły wypłat dla stanowisk do listy płac Szczegóły stanowisk

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_paycycle.cdm\_name                              |
| POSITIONID                     | cdm\_position.cdm\_jobpositionnumber                 |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| ANNUALREGULARHOURS             | cdm\_annualregularhours                             |
| PAIDBYLEGALENTITY              | cdm\_paidby.cdm\_companycode                         |

### <a name="position-default-dimensions-dual-write-to-job-position-dimension"></a>Podwójny zapis pozycja domyślnych wymiarów do Wymiar zadania pozycji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |

### <a name="position-type-to-position-type"></a>Typ stanowisk do Typ stanowiska

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONTYPEID                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| CLASSIFICATION                 | cdm\_classification                                 |

### <a name="position-worker-assignments-v2-to-position-worker-assignment"></a>Przypisanie pracownika do stanowiska V2 do Przypisanie pracownika do stanowiska

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| IsPrimaryPosition              | cdm\_isprimaryposition                              |

### <a name="reason-codes-to-reason-code"></a>Kody przyczyn do kodu przyczyny

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REASONCODEID                   | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISABSENCEAPPLICABLE            | cdm\_isabsenceapplicable                            |
| ISAPPLICATIONAPPLICABLE        | cdm\_isapplicationapplicable                        |
| ISCOMPENSATIONAPPLICABLE       | cdm\_iscompensationapplicable                       |
| ISCREATENEWPOSITIONAPPLICABLE  | cdm\_iscreatenewpositionapplicable                  |
| ISEDITPOSITIONAPPLICABLE       | cdm\_iseditpositionapplicable                       |
| ISHIREAPPLICABLE               | cdm\_ishireapplicable                               |
| ISSKILLMAPPINGAPPLICABLE       | cdm\_isskillmappingapplicable                       |
| ISTERMINATIONAPPLICABLE        | cdm\_isterminationapplicable                        |
| ISTRANSFERAPPLICABLE           | cdm\_istransferapplicable                           |

### <a name="reference-point-setup-line-dual-write-to-compensation-reference-point-setup-line"></a>Linia ustawień punktu odniesienia (podwójny zapis) do linii ustawień punktu odniesienia kompensacji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPTION                    | cdm\_description                                    |
| LINENUM                        | cdm\_linenumber                                     |
| REFPOINTID                     | cdm\_name                                           |
| REFPOINTSETUPID                | cdm\_referencepointsetupid.cdm\_name                 |

### <a name="reference-point-setups-to-compensation-reference-point-setup"></a>Ustawienie punktu odniesienia dla Ustawienia punktu odniesienia kompensacji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REFERENCESETUP                 | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| TYPE                           | cdm\_compensationtype                               |

### <a name="skill-types-to-skill-type"></a>Typy umiejętności do Typu umiejętności

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| SKILLTYPE                      | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="titles-to-title"></a>Tytuły do tytułu

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TITLEID                        | cdm\_name                                           |

### <a name="variable-compensation-level-v2-to-compensation-variable-plan-level"></a>Poziom zmiennej kompensacji V2 do Poziomu Planu zmiennej kompensacji

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AWARDAMOUNT                    | cdm\_awardamount                                    |
| AWARDPERCENT                   | cdm\_awardpercent                                   |
| AWARDUNITSREAL                 | cdm\_awardunits                                     |
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| PLANID                         | cdm\_compensationvariableplanid.cdm\_name            |

### <a name="veteran-status-to-veteran-status"></a>Status weterana do statusu weterana

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VETERANSTATUSID                | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |
| ISPROTECTEDVETERAN             | cdm\_isprotectedveteran                             |

### <a name="work-calendar-enrollments-to-work-calendar-enrollment"></a>Zapisy do kalendarza pracy Zapisy do kalendarza pracy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_employmentid.cdm\_employmentstartdate           |
| PERSONNELNUMBER                | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| CALENDARID                     | cdm\_workcalendarid.cdm\_name                        |
| COMPANYID                      | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |

### <a name="work-calendar-holiday-to-work-calendar-holiday"></a>Kalendarz pracy – wakacje do Kalendarz pracy – wakacje

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ID                             | cdm\_name                                           |
| DESCRIPTION                    | cdm\_description                                    |

### <a name="work-calendar-holiday-line-to-work-calendar-holiday-line"></a>Kalendarz pracy linia wakacyjna do Kalendarz pracy linia wakacyjna

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| HOLIDAYID                      | cdm\_workcalendarholidayid.cdm\_name                 |
| NAME                           | cdm\_name                                           |
| HOLIDAYDATE                    | cdm\_holidaydate                                    |

### <a name="worker-to-worker"></a>Pracownik do Pracownika

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workernumber                                   |
| FIRSTNAME                      | cdm\_firstname                                      |
| MIDDLENAME                     | cdm\_middlename                                     |
| LASTNAME                       | cdm\_lastname                                       |
| WORKERTYPE                     | cdm\_type                                           |
| WORKERSTATUS                   | cdm\_status                                         |
| PRIMARYCONTACTEMAIL            | cdm\_primaryemailaddress                            |
| PRIMARYCONTACTPHONE            | cdm\_primarytelephone                               |
| PRIMARYCONTACTFACEBOOK         | cdm\_facebookidentity                               |
| PRIMARYCONTACTTWITTER          | cdm\_twitteridentity                                |
| PRIMARYCONTACTLINKEDIN         | cdm\_linkedinidentity                               |
| PRIMARYCONTACTURL              | cdm\_websiteurl                                     |
| GENDER                         | cdm\_gender                                         |
| BIRTHDATE                      | cdm\_birthdate                                      |
| NAME                           | cdm\_fullname                                       |

### <a name="worker-bank-accounts-to-worker-bank-account"></a>Konta bankowe pracownika do konta bankowego pracownika

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATION          | cdm\_accountidentification                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONID         | cdm\_countryorregion                                |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSDISTRICTNAME            | cdm\_districtname                                   |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| BANKACCOUNTNUMBER              | cdm\_bankaccountnumber                              |
| BANKACCOUNTTYPE                | cdm\_bankaccounttype                                |
| EMAIL                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| ROUTINGNUMBER                  | cdm\_routingnumber                                  |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telexnumber                                    |
| BANKIBAN                       | cdm\_iban                                           |
| SWIFTNO                        | cdm\_swiftcode                                      |
| BANKLOCATIONCODE               | cdm\_banklocationcode                               |
| BRANCHNAME                     | cdm\_branchname                                     |
| BRANCHNUMBER                   | cdm\_branchnumber                                   |
| ROUTINGNUMBERTYPE              | cdm\_routingnumbertype                              |
| ACCOUNTHOLDER                  | cdm\_accountholder                                  |
| NAMEOFPERSON                   | cdm\_nameofperson                                   |
| NAME                           | cdm\_description                                    |
| ADDRESSSTREET                  | cdm\_line1                                          |
| ADDRESSSTREETNUMBER            | cdm\_line2                                          |

### <a name="worker-personal-details-to-worker-personal-detail"></a>Dane osobowe pracownika do danych osobistych pracownika

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| BIRTHDATE                      | cdm\_birthdate                                      |
| PERSONBIRTHCITY                | cdm\_birthcity                                      |
| GENDER                         | cdm\_gender                                         |
| EXPATRIATEENDDATE              | cdm\_expatriateenddate                              |
| EXPATRIATESTARTDATE            | cdm\_expatriatestartdate                            |
| DISABLEDVETERAN                | cdm\_isdisabledveteran                              |
| DECEASEDDATE                   | cdm\_deceaseddate                                   |
| DISABLEDVERIFICATIONDATE       | cdm\_disabledveteranverificationdate                |
| EDUCATION                      | cdm\_education                                      |
| ETHNICORIGINID                 | cdm\_ethnicoriginid.cdm\_name                        |
| ISDISABLED                     | cdm\_isdisabled                                     |
| ISFULLTIMESTUDENT              | cdm\_isfulltimestudent                              |
| ISEXPATRIATERULINGAPPLICABLE   | cdm\_isexpatriaterulingapplicable                   |
| MARITALSTATUS                  | cdm\_maritalstatus                                  |
| MILITARYSERVICESTARTDATE       | cdm\_militaryservicestartdate                       |
| MILITARYSERVICEENDDATE         | cdm\_militaryserviceenddate                         |
| NUMBEROFDEPENDENTS             | cdm\_numberofdependents                             |
| NATIVELANGUAGEID               | cdm\_nativelanguageidid.cdm\_name                    |
| NATIONALITYCOUNTRYREGION       | cdm\_nationalitycountryregion                       |
| PERSONBIRTHCOUNTRYREGION       | cdm\_birthcountryregion                             |
| FATHERBIRTHCOUNTRYREGION       | cdm\_fatherbirthcountryregion                       |
| MOTHERBIRTHCOUNTRYREGION       | cdm\_motherbirthcountryregion                       |
| CITIZENSHIPCOUNTRYREGION       | cdm\_citizenshipcountryregion                       |
| VETERANSTATUSID                | cdm\_veteranstatusid.cdm\_name                       |

### <a name="worker-postal-addresses-dual-write-to-worker-address"></a>Adresy pocztowe pracowników z podwójnym zapisem na adres pracownika

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PERSONNELNUMBER                | cdm\_workerid.cdm\_workernumber                      |
| ADDRESSLOCATIONID              | cdm\_addressnumber                                  |
| ADDRESSLOCATIONROLES           | cdm\_addresstype                                    |
| EFFECTIVE                      | cdm\_effectivedate                                  |
| EXPIRATION                     | cdm\_expirationdate                                 |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSSTREETNUMBER            | cdm\_streetnumber                                   |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSCOUNTYID                | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_description                                    |
| ADDRESSLATITUDE                | cdm\_latitude                                       |
| ADDRESSLONGITUDE               | cdm\_longitude                                      |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ISPRIMARY                      | cdm\_ispreferred                                    |

### <a name="working-time-to-work-calendar-time-interval"></a>Czas pracy do przedziału czasowego w kalendarzu pracy

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ENDTIME                        | cdm\_endtime                                        |
| STARTTIME                      | cdm\_starttime                                      |
| WORKCALENDARDATE               | cdm\_workcalendardayid.cdm\_calendardate             |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKCALENDARID                 | cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name  |

### <a name="working-times-to-work-calendar-day"></a>Czas pracy do dnia kalendarzowego

| Encja Finance                 | Tabela usługi Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARDATE                   | cdm\_calendardate                                   |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKINGDAYDEFINITION           | cdm\_status                                         |

## <a name="integration-considerations"></a>Uwagi dotyczące integracji

- Wszystkie zmiany dokonywane w danych w jednym z systemów będą podlegały zatwierdzeniu przez drugi system. Jeśli wystąpi błąd, dane nie zostaną zapisane w żadnym systemie. 
- Wszystkie zapisy podlegają domyślnym ustawieniom danych (jeśli w Finance występuje logika niestandardowa).
- Aplikacja integratora podwójnego zapisu wykorzystuje klucze integracyjne do mapowania między dwoma systemami. Czasami trudno jest wybrać właściwy klucz integracyjny, zwłaszcza jeśli wymagania spełnia kilka kluczy integracyjnych. Aby ułatwić ten wybór, w poniższej tabeli przedstawiono sugerowane klucze integracyjne dla mapowań.

| Tabela usługi Dataverse                          | Klucze integracji |
|------------------------------------------|------------------|
| Wypłata na konto bankowe                | cdm\_bankaccountid.cdm\_accountidentification, cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Częstotliwość obliczania świadczeń            | cdm\_name |
| Częstotliwość obliczania okresu płac dla świadczeń | cdm\_payperiodid.cdm\_periodstartdate, cdm\_payperiodid.cdm\_paycycleid.cdm\_name, cdm\_benefitcalculationfrequencyid.cdm\_name |
| Stawka obliczania świadczenia                 | cdm\_name |
| Szczegół stawki obliczania świadczenia          | cdm\_workerdeduction, cdm\_effective, cdm\_calculationrateid.cdm\_name |
| Opcja świadczenia                           | cdm\_name |
| Typ świadczenia                             | cdm\_name |
| Kalendarz procesu biznesowego                | cdm\_name |
| Przypisanie grupy procesu biznesowego        | cdm\_name |
| Nagłówek procesu biznesowego                  | cdm\_processid |
| Grupa zadań biblioteki procesów biznesowych      | cdm\_processtype, cdm\_name |
| Etap procesu biznesowego                   | cdm\_name, cdm\_businessprocesstype, cdm\_companyid.cdm\_companycode |
| Zadanie procesu biznesowego                    | cdm\_taskid |
| Jednostka biznesowa                            | |
| Nagłówek szablonu listy kontrolnej                | cdm\_businessprocesstype, cdm\_name, cdm\_genericsubtype |
| Zadanie szablonu listy kontrolnej                  | cdm\_taskid |
| Firma                                  | cdm\_companycode |
| System stałych wynagrodzeń                  | cdm\_name, cdm\_company.cdm\_companycode |
| Siatka wynagrodzeń                        | cdm\_name, cdm\_companyid.cdm\_companycode |
| Poziom wynagrodzeń                       | cdm\_name |
| Wynagrodzenie — częstotliwość wypłat               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Ustawianie punktów odniesienia kompensacji       | cdm\_name, cdm\_companyid.cdm\_companycode |
| Wiersz ustawień punktów odniesienia kompensacji  | cdm\_name, cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode |
| Region wynagrodzenia                      | cdm\_name |
| Struktura wynagrodzeń                   | cdm\_compensationlevelid.cdm\_name, cdm\_referencepointid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_compensationgridid.cdm\_name, cdm\_compensationgridid.cdm\_companyid.cdm\_companycode |
| Plan wynagrodzeń o zmiennej wysokości               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Poziom planu wynagrodzeń o zmiennej wysokości         | cdm\_companyid.cdm\_companycode, cdm\_compensationvariableplanid.cdm\_name, cdm\_compensationvariableplanid.cdm\_companyid.cdm\_companycode, cdm\_compensationlevelid.cdm\_name |
| Typ planu wynagrodzeń o zmiennej wysokości          | cdm\_name, cdm\_companyid.cdm\_companycode |
| Waluta                                 | isocurrencycode |
| Dział                               | cdm\_departmentnumber |
| Zatrudnienie                               | cdm\_employmentstartdate, cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Pochodzenie etniczne                            | cdm\_name |
| Zdarzenie dotyczące stałego wynagrodzenia                 | cdm\_name, cdm\_companyid.cdm\_companycode |
| Funkcja                                      | cdm\_name |
| Czynności związane z funkcją                             | cdm\_name |
| Stanowisko pracy                             | cdm\_jobpositionnumber |
| Wymiar stanowiska pracy                   | cdm\_jobpositionid.cdm\_jobpositionnumber, cdm\_companyid.cdm\_companycode |
| Typ funkcji                                 | cdm\_name |
| Język                                 | cdm\_name |
| Transakcja banku urlopów                   | cdm\_transactiondate, cdm\_transactiontype, cdm\_transactionnumber, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Rejestracja urlopu                         | cdm\_startdate, cdm\_leaveplanid.cdm\_name, cdm\_leaveplanid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Plan urlopów                               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Wniosek urlopowy                            | cdm\_leaverequestnumber, cdm\_companyid.cdm\_companycode |
| Szczegół wniosku urlopowego                     | cdm\_leavedate, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_leaverequestid.cdm\_leaverequestnumber, cdm\_leaverequestid.cdm\_companyid.cdm\_companycode |
| Typ urlopu                               | cdm\_type, cdm\_companyid.cdm\_companycode |
| Kod przyczyny typu nieobecności                   | cdm\_reasoncodeid.cdm\_name, cdm\_typeid.cdm\_type, cdm\_typeid.cdm\_companyid.cdm\_companycode |
| Nagłówek procesu wdrażania do pracy                   | cdm\_processheaderid.cdm\_processid |
| Organizacja                             | |
| Cykl kalkulacji płac                                | cdm\_name |
| Okres kalkulacji płac                               | cdm\_periodstartdate, cdm\_paycycleid.cdm\_name, cdm\_periodenddate |
| Kod zarobków dla listy płac                     | cdm\_name |
| Szczegół stanowiska listy płac                  | cdm\_validfrom, cdm\_validto, cdm\_position.cdm\_jobpositionnumber |
| Agencja wystawiająca identyfikator osoby     | cdm\_name |
| Typ stanowiska                            | cdm\_name |
| Przypisanie pracownika do stanowiska               | cdm\_validfrom, cdm\_jobpositionid.cdm\_jobpositionnumber |
| Kod przyczyny                              | cdm\_name |
| Typ kwalifikacji                               | cdm\_name |
| Region podatkowy                               | cdm\_stateorprovince, cdm\_name, cdm\_countryorregion, cdm\_county, cdm\_city |
| Zespół                                     | azureactivedirectoryobjectid, membershiptype |
| Nazwa                                    | cdm\_name |
| Użytkownik                                     | azureactivedirectoryobjectid |
| Reguła wypłat                             | cdm\_name, cdm\_companyid.cdm\_companycode |
| Status kombatanta                           | cdm\_name |
| Kalendarz pracy                            | cdm\_name, cdm\_companyid.cdm\_companycode |
| Dzień w kalendarzu roboczym                        | cdm\_calendardate, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Rejestracja w kalendarzu pracy                 | cdm\_employmentid.cdm\_employmentstartdate, cdm\_employmentid.cdm\_workerid.cdm\_workernumber, cdm\_employmentid.cdm\_companyid.cdm\_companycode |
| Święto w kalendarzu pracy                    | cdm\_name |
| Wiersz dnia wolnego w kalendarzu roboczym               | cdm\_holidaydate, cdm\_workcalendarholidayid.cdm\_name |
| Zakres czasu w kalendarzu roboczym              | cdm\_starttime, cdm\_workcalendardayid.cdm\_calendardate, cdm\_workcalendardayid.cdm\_companyid.cdm\_companycode, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Pracownik                                   | cdm\_workernumber |
| Adres pracownika                           | cdm\_addressnumber, cdm\_addresstype, cdm\_workerid.cdm\_workernumber |
| Konto bankowe pracownika                      | cdm\_accountidentification, cdm\_workerid.cdm\_workernumber |
| Stałe wynagrodzenie pracownika                | cdm\_linenumber, cdm\_effectivedate, cdm\_companyid.cdm\_companycode, cdm\_positionid.cdm\_jobpositionnumber, cdm\_workerid.cdm\_workernumber, cdm\_eventid.cdm\_name, cdm\_eventid.cdm\_companyid.cdm\_companycode, cdm\_planid.cdm\_name, cdm\_planid.cdm\_company.cdm\_companycode |
| Numer dokumentu identyfikacyjnego pracownika      | cdm\_identificationnumber, cdm\_workerid.cdm\_workernumber, cdm\_identificationtypeid.cdm\_name |
| Typ dokumentu identyfikacyjnego pracownika        | cdm\_name |
| Dane osobowe pracownika                   | cdm\_workerid.cdm\_workernumber |
