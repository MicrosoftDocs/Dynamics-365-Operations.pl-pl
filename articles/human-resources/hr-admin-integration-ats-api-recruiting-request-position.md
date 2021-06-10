---
title: Stanowisko wniosku o rekrutację
description: W tym temacie opisano jednostkę Wniosku o rekrutację na stanowisko dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a709b8fb2f22c0e7a81399349cacbcfbfc91c8b2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059263"
---
# <a name="recruiting-request-position"></a>Stanowisko wniosku o rekrutację

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Wniosku o rekrutację na stanowisko dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>opis

Opisuje stanowisko lub stanowiska do wypełnienia w przypadku wniosku o rekrutację. Dodanie stanowiska do wniosku o rekrutację jest opcjonalne. Właściwości stanowiska są tylko do odczytu, ponieważ właściwości stanowiska nie powinny różnić się we wniosku rekrutacji niż w rekordzie głównym stanowiska. Jeśli właściwości wymagają zmiany, należy to zrobić w rekordzie głównym stanowiska przed dodaniem stanowiska do wniosku rekrutacyjnego.

### <a name="json-representation"></a>Reprezentacja JSON
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator podmiotu żądanego stanowiska rekrutacyjnego**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne |    Wygenerowany przez system identyfikator rekordu stanowiska dla wniosku o rekrutację. |
| **Identyfikator wniosku o rekrutację**<br>mshr_recruitingrequestid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Odczytywalny przez użytkownika unikatowy identyfikator wniosku o rekrutację. |
| **Wartość identyfikatora wniosku o rekrutację**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmrecruitingrequestentityid należący do jednostki mshr_hcmrecruitingrequestentity | Wygenerowany przez system identyfikator wniosku rekrutacyjnego, do którego przypisane jest stanowisko. |
| **Identyfikator stanowiska**<br>mshr_positionid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Odczytywalny przez użytkownika unikatowy identyfikator stanowiska. |
| **Wartość identyfikatora stanowiska**<br>_mshr_fk_position_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmpositionv2entityid jednostki mshr_hcmpositionv2entity | Wygenerowany przez system identyfikator stanowiska. |
| **Opis**<br>mshr_description<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Opis stanowiska. |
| **Identyfikator typu stanowiska**<br>mshr_positiontypeid<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Czytelny dla użytkownika niepowtarzalny identyfikator typu pozycji dla tego stanowiska. |
| **Wartość identyfikatora typu stanowiska**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmpositiontypeentityid jednostki mshr_hcmpositiontypeentity | Wygenerowany przez system unikalny identyfikator typu pozycji dla tej pozycji. |
| **Stan**<br>mshr_status<br>Zestaw opcji *RecruitingRequestPositionStatus* | Czytaj/zapisz<br>Potrzebne | Stan stanowiska w zgłoszeniu rekrutacyjnym. |
| **Numer działu**<br>mshr_departmentnumber<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny<br> | Numer działu stanowiska. |
| **Wartość identyfikatora działu**<br>_mshr_fk_department_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_omdepartmententityid jednostki mshr_omdepartmententity | Wygenerowany przez system unikalny identyfikator działu stanowiska. |
| **Identyfikator stanowiska zwierzchniego**<br>mshr_reportstopositionid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Czytelny dla użytkownika identyfikator stanowiska, do którego zgłasza się rekrutowane stanowisko w hierarchii organizacyjnej. |
| **Wartość identyfikatora stanowiska zwierzchniego**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmpositionv2entityid jednostki mshr_hcmpositionv2entity | Wygenerowany przez system identyfikator stanowiska, do którego przynależy stanowisko w procesie rekrutacji. |
| **Numer personelu przełożonego**<br>mshr_reportstopersonnelnumber<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Identyfikator pracownika, do którego ma być zgłaszany zatrudniony kandydat. |
| **Wartość identyfikatora pracownika zwierzchniego**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmworkerbaseentityid jednostki mshr_hcmworkerbaseentity | Wygenerowany przez system identyfikator pracownika, do którego ma być zgłaszany zatrudniony kandydat. |
| **Wymiar finansowy**<br>mshr_financialdimension<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Wymiar finansowy (na przykład miejsce powstawania kosztów) przypisany do stanowiska. Wymiar finansowy jest przypisywany do każdej pozycji na firmę. Centra kosztów zdefiniowane w wymiarach są dostępne za pośrednictwem jednostki mshr_dimattributeomcostcenterentity. |
| **Identyfikator obszaru danych**<br>mshr_dataareaid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Określa firmę (przedsiębiorstwo) dla wniosku o rekrutację na stanowisko. |
| **Wartość identyfikatora obszaru danych**<br>_mshr_dataareaid_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: cdm_companyid jednostki cdm_company obcej | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę) dla wniosku rekrutacyjnego na stanowisko. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Łączenie wartości żądania rekrutacji i identyfikatora pozycji jako kolejna metoda unikalnej identyfikacji rekordu. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]