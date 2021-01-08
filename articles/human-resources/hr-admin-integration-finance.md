---
title: Konfigurowanie integracji z rozwiązaniem Finance
description: W tym artykule opisano dostępne funkcje integracji między rozwiązaniami Dynamics 365 Human Resources i Dynamics 365 Finance.
author: andreabichsel
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b4d6369ab567879e23e1f132265aaff45c8ce47
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527929"
---
# <a name="configure-integration-with-finance"></a>Konfigurowanie integracji z rozwiązaniem Finance

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Aby zintegrować Dynamics 365 Human Resources z Dynamics 365 Finance, można skorzystać z szablonu Human Resources do Finance w [Integratorze danych](https://docs.microsoft.com/powerapps/administrator/data-integrator). Szablon Human Resources do Finance umożliwia przepływ danych dla zadań, stanowisk i pracowników. Szablon umożliwia przepływ danych z Human Resources do Finance, ale nie pozwala na przepływ danych z Finance do Human Resources.

![Przepływ integracji z programu Human Resources do programu Finance](./media/hr-admin-integration-finance-flow.png)

Rozwiązanie Z Human Resources do Finance oferuje następujące rodzaje synchronizacji danych:

- Zarządzanie zadaniami w Human Resources i synchronizowanie ich z Human Resources do Finance
- Zarządzanie stanowiskami i przypisaniami stanowisk w Human Resources oraz synchronizowanie ich z Human Resources do Finance
- Zarządzanie etatami w Human Resources i synchronizowanie ich z Human Resources do Finance
- Zarządzanie pracownikami i adresami pracowników w Human Resources oraz synchronizowanie ich z Human Resources do Finance

## <a name="system-requirements-for-human-resources"></a>Wymagania systemowe modułu Human Resources

Rozwiązanie integracyjne wymaga następujących wersji modułu Human Resources i aplikacji Finance: 

- Dynamics 365 Human Resources w tabeli Common Data Service
- Dynamics 365 Finance, wersja 7.2 lub nowsza

## <a name="template-and-tasks"></a>Szablon i zadania

Aby uzyskać dostęp do szablonu Z Human Resources do Finance.

1. Otwórz [Centrum administracyjne usługi Power Apps](https://admin.powerapps.com/). 

2. Wybierz **Projekty**, a następnie wybierz opcję **Nowy projekt** w prawym górnym rogu. Dla każdej firmy, która ma zostać zintegrowana z Finance, należy utworzyć nowy projekt.

3. Wybierz **Human Resources (Human Resources Common Data Service do Finance)**, aby synchronizować rekordy z Human Resources do Finance.

Szablon używa poniższych podstawowcy zadań do synchronizowania rekordów z Human Resources do Finance:

- **Z Funkcje stanowisk do Wynagrodzenie — funkcja stanowiska**
- **Z Działy do Jednostka operacyjna**
- **Z Typy funkcji do Wynagrodzenie — typ stanowiska**
- **Z Funkcje do Funkcje**
- **Z Funkcje do Szczegóły funkcji**
- **Z Typy stanowisk do Typ stanowiska**
- **Ze Stanowiska funkcji do Bazowe stanowisko**
- **Ze Stanowiska funkcji do Szczegóły stanowiska**
- **Ze Stanowiska funkcji do Okresy ważności stanowisk**
- **Ze Stanowiska funkcji do Hierarchii stanowisk**
- **Z Pracownik do Pracownik**
- **Z Etaty do Zatrudnienie**
- **Z Etaty do Szczegóły zatrudnienia**
- **Z Przypisanie pracownika do stanowiska do Przypisania pracowników do stanowisk**
- **Z Adresy pracowników do Adres pocztowy pracownika wer. 2**

## <a name="template-mappings"></a>Mapowania w szablonie

W poniższych tabelach mapowania szablonów nazwa zadania zawiera jednostki używane w poszczególnych aplikacjach. Źródło (Human Resources) znajduje się po lewej stronie, a miejsce docelowe (Finance) po prawej.

### <a name="job-functions-to-compensation-job-function"></a>Z Funkcje stanowisk do Wynagrodzenie — funkcja stanowiska

| Jednostka usługi Common Data Service (źródło) | Jednostka finansowa (lokalizacja docelowa) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Nazwa funkcji)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | DESCRIPTION   (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>Z Działy do Jednostka operacyjna

| Jednostka usługi Common Data Service (źródło)           | Jednostka finansowa (lokalizacja docelowa) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Z Typy funkcji do Wynagrodzenie — typ stanowiska

| Jednostka usługi Common Data Service (źródło)   | Jednostka finansowa (lokalizacja docelowa) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | DESCRIPTION   (DESCRIPTION)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Z Funkcje do Funkcje

| Jednostka usługi Common Data Service (źródło)                           | Jednostka finansowa (lokalizacja docelowa)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | DESCRIPTION   (DESCRIPTION)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Z Funkcje do Szczegóły funkcji

| Jednostka usługi Common Data Service (źródło)                             | Jednostka finansowa (lokalizacja docelowa) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Typ funkcji (Nazwa typu funkcji))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Funkcja stanowiska (Nazwa funkcji stanowiska)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (Początek ważności)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Koniec ważności)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Domyślnie w przeliczeniu na pełen etat)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Z Typy stanowisk do Typ stanowiska

| Jednostka usługi Common Data Service (źródło)       | Jednostka finansowa (lokalizacja docelowa) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | DESCRIPTION   (DESCRIPTION)                 |
| cdm_classification   (cdm_classification) | CLASSIFICATION   (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>Ze Stanowiska funkcji do Bazowe stanowisko

| Jednostka usługi Common Data Service (źródło)           | Jednostka finansowa (lokalizacja docelowa) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Numer stanowiska funkcji) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Ze Stanowiska funkcji do Szczegóły stanowiska

| Jednostka usługi Common Data Service (źródło)              | Jednostka finansowa (lokalizacja docelowa)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Numer stanowiska funkcji)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Funkcja (Nazwa))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | DESCRIPTION   (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber   (Dział (Numer działu)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Typ stanowiska (Nazwa))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (Dostępne do przypisania)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (Początek ważności)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto (Koniec ważności)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (W przeliczeniu na pełen etat)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Ze Stanowiska funkcji do Okresy ważności stanowisk

| Jednostka usługi Common Data Service (źródło)             | Jednostka finansowa (lokalizacja docelowa) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Numer stanowiska funkcji)   | POSITIONID (POSITIONID)                      |
| Obliczona aktywacja (Obliczona aktywacja) | VALIDFROM (VALIDFROM)                        |
| Obliczona emerytura (Obliczona emerytura) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Ze Stanowiska funkcji do Hierarchii stanowisk

| Jednostka usługi Common Data Service (źródło)        | Jednostka finansowa (lokalizacja docelowa) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Numer stanowiska funkcji)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (Początek ważności)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Koniec ważności)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Z Pracownik do Pracownik
| Jednostka usługi Common Data Service (źródło)           | Jednostka finansowa (lokalizacja docelowa)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | BIRTHDATE   (BIRTHDATE)                           |
| cdm_gender   (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL)      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | FIRSTNAME   (FIRSTNAME)                           |
| cdm_middlename   (cdm_middlename)             | MIDDLENAME   (MIDDLENAME)                         |
| cdm_lastname   (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE   (WORKERTYPE)                         |
| cdm_state   (cdm_state)                       | WORKSTATUS   (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>Z Etaty do Zatrudnienie

| Jednostka usługi Common Data Service (źródło)                             | Jednostka finansowa (lokalizacja docelowa) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Z Etaty do Szczegóły zatrudnienia

| Jednostka usługi Common Data Service (źródło)                             | Jednostka finansowa (lokalizacja docelowa)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)       |
| cdm_validfrom   (Początek ważności)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Koniec ważności)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | WORKERSTARTDATE   (WORKERSTARTDATE)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | LASTDATEWORKED   (LASTDATEWORKED)             |
| cdm_transitiondate   (cdm_transitiondate)                       | TRANSITIONDATE   (TRANSITIONDATE)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE   (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE   (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT   (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount   (cdm_workernoticeamount)              | WORKERNOTICEAMOUNT   (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Z Przypisanie pracownika do stanowiska do Przypisania pracowników do stanowisk

| Jednostka usługi Common Data Service (źródło)                             | Jednostka finansowa (lokalizacja docelowa)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Numer stanowiska funkcji)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (Początek ważności)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Koniec ważności)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Z Adresy pracowników do Adres pocztowy pracownika wer. 2

| Jednostka usługi Common Data Service (źródło)                             | Jednostka finansowa (lokalizacja docelowa)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSLOCATIONROLES   (ADDRESSLOCATIONROLES) |
| cdm_line1   (cdm_line1)                                         | ADDRESSSTREET   (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY   (ADDRESSCITY)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ADDRESSSTATE   (ADDRESSSTATE)                 |
| cdm_postalcode   (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion   (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber   (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>Uwagi dotyczące integracji

Proces integracji z Human Resources do Finance będzie próbował dopasować rekordy na podstawie identyfikatorów. Jeśli takie dopasowania zostaną znalezione, Integrator danych zastępuje dane w Finance wartościami z Human Resources. Jednak może wystąpić problem, jeśli logicznie są to różne rekordy, a ten sam identyfikator został wygenerowany w Human Resources lub Finance na podstawie odpowiedniej numeracji.

Ten problem może nastąpić z obszarem **Pracownik**, gdzie do wykonania dopasowania jest używany **Numer pracownika** oraz **Stanowiska**. W obszarze Funkcje nie są używane sekwencje numerów. W efekcie jeśli ten sam identyfikator funkcji istnieje zarówno w Human Resources, jak i w Finance, informacje z Human Resources zastąpią informacje w Dynamics 365 Finance. 

Aby zapobiec problemom ze zduplikowanymi identyfikatorami, można w [numeracji](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=/dynamics365/unified-operations/talent/toc.json) dodać prefiks albo określić w niej numer początkowy, który wykracza poza zakres drugiego systemu. 

Identyfikator lokalizacji używany w adresie pracownika nie jest częścią numeracji. Jeśli podczas integrowania adresu pracownika z modułu Human Resources do aplikacji Finance adres pracownika już istnieje w aplikacji Finance, może zostać utworzony zduplikowany rekord adresu. 

Poniższa ilustracja przedstawia przykład mapowania w szablonie w Integratorze danych. 

![Mapowanie w szablonie](./media/IntegrationMapping.png)