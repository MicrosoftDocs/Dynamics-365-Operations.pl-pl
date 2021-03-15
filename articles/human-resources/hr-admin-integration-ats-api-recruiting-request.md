---
title: Wniosek o rekrutację
description: W tym temacie opisano jednostkę Wniosku o rekrutację dla Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 572ee0755e331d19b41442e3614effb92db95a92
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125432"
---
# <a name="recruiting-request"></a>Wniosek o rekrutację

W tym temacie opisano jednostkę Wniosku o rekrutację dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequestentity

### <a name="description"></a>opis

Opisuje żądanie rekrutacji na stanowisko.

### <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator wniosku o rekrutację**<br>mshr_recruitingrequestid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Czytelny przez użytkownika unikatowy identyfikator żądania wyświetlany w aplikacji kadr. Sekwencja numerów. |
| **Identyfikator jednostki wniosku o rekrutację**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania wniosku o rekrutację. |
| **Identyfikator obszaru danych**<br>mshr_dataareaid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny<br> | Określa firmę (firmę) dla wniosku o rekrutację. |
| **Wartość identyfikatora obszaru danych**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: cdm_companyid jednostki cdm_company obcej | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę) dla żądania rekrutacyjnego. |
| **Identyfikator pracownika menedżera zatrudniającego**<br>mshr_hiringmanagerpersonnelnumber<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer personelu menedżera ds. zatrudniania skojarzonego z tym wnioskiem o rekrutację. |
| **Wartość identyfikatora menedżera ds. zatrudniania**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmworkerbaseentityid jednostki mshr_hcmworkerbaseentity | Wygenerowana przez system wartość identyfikatora GUID służąca do identyfikacji menedżera powiązanego z żądaniem rekrutacyjnym. |
| **Numer strony rekrutującej**<br>mshr_recruiterpartynumber<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer osoby (strony) osoby rekrutacji wybranej dla żądania. |
| **Wartość identyfikatora rekrutacji**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowana przez system wartość identyfikatora GUID służąca do identyfikacji osoby prowadzącej rozmowę kwalifikacyjną powiązanej z żądaniem rekrutacyjnym. |
| **Stan**<br>mshr_status<br>Zestaw opcji *RecruitingRequestStatus* | Czytaj/zapisz<br>Potrzebne<br> | Wskazuje stan wniosku o rekrutację. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opisuje żądanie. |
| **Identyfikator lokalizacji wniosku o rekrutację**<br>mshr_recruitingrequestlocationid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Czytelny przez użytkownika unikatowy identyfikator lokalizacji zadania skojarzonej z tym żądaniem. |
| **Wartość identyfikatora lokalizacji rekrutacji**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmrecruitingrequestlocationentityid należący do jednostki mshr_hcmrecruitingrequestlocationentity | Wygenerowana przez system wartość identyfikatora GUID służąca do identyfikacji lokalizacji żądania rekrutacji wybranej dla żądania. |
| **Komentarze**<br>mshr_comments<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Komentarze dotyczące wniosku, do użycia przez menedżerów rekrutacji i rekruterów. |
| **Identyfikator stanowiska**<br>mshr_jobid<br>*Ciąg* | Odpisz raz<br>Potrzebne |   Czytelny dla użytkownika unikalny identyfikator zadania współdzielonego przez wszystkie stanowiska powiązane z tym żądaniem. |
| **Wartość identyfikatora zadania**<br>_mshr_fk_job_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmjobentityid jednostki mshr_hcmjobentity | Wygenerowany przez system unikatowy identyfikator stanowiska, współdzielony przez wszystkie stanowiska powiązane z wnioskiem rekrutacyjnym. |
| **Identyfikator tytułu**<br>mshr_titleid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Czytelny przez użytkownika unikatowy identyfikator stanowiska skojarzonego z tym żądaniem. |
| **Wartość identyfikatora tytułu**<br>_mshr_fk_title_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmtitleid jednostki mshr_hcmtitleentity | Wygenerowany przez system unikalny identyfikator tytułu stanowiska wybranego do zlecenia rekrutacyjnego. |
| **Identyfikator funkcji stanowiska**<br>mshr_jobfunctionid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_jobfunctionid jednostki mshr_hcmjobfunctionentity | Czytelny przez użytkownika unikatowy identyfikator funkcji stanowiska skojarzonej z tym żądaniem. |
| **Domyślny ekwiwalent pełnego czasu pracy**<br>mshr_defaultfulltimeequivalency<br>*Podwójne* | Tylko do odczytu<br>Potrzebne | Wartość ekwiwalentu pełnego czasu pracy dla zadania, gdzie 1,0 oznacza pracownika zatrudnionego na pełen etat. |
| **Kategoria stanowisk prawnych**<br>mshr_regulatoryjobcategory<br>Zestaw opcji *RegulatoryJobCategory* | Tylko do odczytu<br>Opcjonalny | Kategoria stanowiska EEO dla stanowiska wybranego dla stanowiska. Prawidłowe wartości uwzględnione w zestawie opcji HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory). |
| **Identyfikator typu zadania**<br>mshr_jobtypeid<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Typ stanowiska związany ze stanowiskiem. Typy zadań to wartości definiowane przez użytkownika, dostępne w jednostce mshr_hcmjobtypeentity. |
| **Wartość identyfikatora typu zadania**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmjobtypeentityid jednostki mshr_hcmjobtypenentity | Wygenerowany przez system unikalny identyfikator typu stanowiska powiązanego ze stanowiskiem dla żądania rekrutacyjnego. |
| **Stan zwolnienia**<br>mshr_exemptstatus<br>Zestaw opcji *JobExemptStatus* | Tylko do odczytu<br>Opcjonalny | Stan zwolnienia FLSA na podstawie typu zadania. |
| **Szacowana data rozpoczęcia**<br>mshr_estimatedstartdate<br>*Data* | Czytaj/zapisz<br>Potrzebne | Szacowana data rozpoczęcia pracy przez kandydata. |
| **Zewnętrzny opis**<br>mshr_externaldescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis pracy / stanowiska skierowany do kandydata. | Wynagrodzenie - niski próg<br>mshr_compensationlowthreshold<br>*Podwójne* | Czytaj/zapisz<br>Opcjonalny | Dolna granica poziomu wynagrodzenia. |
| **Punkt kontrolny wynagrodzenia**<br>mshr_compensationcontrolpoint<br>*Podwójne* | Czytaj/zapisz<br>Opcjonalny | Punkt kontrolny dla poziomu wynagrodzeń. |
| **Wynagrodzenie - wysoki próg**<br>mshr_compensationhighthreshold<br>*Podwójne* | Czytaj/zapisz<br>Opcjonalny | Górna granica poziomu wynagrodzenia. |
| **Poziom wynagrodzeń**<br>mshr_compensationlevelid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Poziom wynagrodzenia na stanowisku. Stanowisko może być ustawione z wieloma poziomami wynagrodzeń. Ten atrybut wskazuje wybrany poziom wynagrodzenia dla tego żądania. |
| **Identyfikator wynagrodzenia stanowiska**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmjobcompensationentityid jednostki mshr_hcmjobcompensationentity | Wygenerowany przez system unikatowy identyfikator poziomu wynagrodzenia skojarzonego ze stanowiskiem zlecenia rekrutacyjnego. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]