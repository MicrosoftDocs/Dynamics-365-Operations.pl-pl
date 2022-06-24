---
title: Rekrutacja wymaga edukacji
description: W tym artykule opisano jednostkę Rekrutacja wymaga edukacji dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: bcdb5e2cc61ce551af21401ea34d8e85bc21fc6c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893853"
---
# <a name="recruiting-request-education"></a>Rekrutacja wymaga edukacji


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Rekrutacja wymaga edukacji dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>opis

Opisuje wymagania edukacyjne dla RecruitingRequest.

### <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki rekrutacji wymagającej edukacji**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikalny identyfikator rekordu Edukacji we wniosku rekrutacji. |
| **Identyfikator wniosku o rekrutację**<br>mshr_recruitingrequestid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Odczytywalny przez użytkownika unikatowy identyfikator powiązanego wniosku o rekrutację. |
| **Wartość identyfikatora wniosku o rekrutację**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmrecruitingrequestentityid należący do jednostki mshr_hcmrecruitingrequestentity | Wygenerowany przez system unikalny identyfikator powiązanego wniosku rekrutacyjnego. |
| **Identyfikator poziomu wykształcenia**<br>mshr_educationlevelid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Wymagany poziom wykształcenia. |
| **Wartość identyfikatora poziomu wykształcenia**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmeducationlevelentityid jednostki mshr_hcmeducationlevelentity | Wygenerowany przez system unikalny identyfikator wymaganego poziomu wykształcenia. |
| **Opis poziomu wykształcenia**<br>mshr_educationleveldescription<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Opis poziomu wymaganego dla umiejętności. |
| **Identyfikator dziedziny wykształcenia**<br>mshr_educationdisciplinedescription<br>*Ciąg* | Odpisz raz<br>Potrzebne | Obszar dziedziny wykształcenia. |
| **Wartość identyfikatora dziedziny wykształcenia**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmeducationdisciplineentityid jednostki mshr_hcmeducationdisciplineentity | Wygenerowany przez system unikalny identyfikator obszaru dyscypliny edukacyjnej. |
| **Opis dyscypliny edukacji**<br>mshr_educationdisciplinedescription<br>Ciąg | Tylko do odczytu<br>Potrzebne | Opis dziedziny wykształcenia. |
| **Identyfikator obszaru danych**<br>mshr_dataareaid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Określa osobę prawną (firmę).|
| **Wartość identyfikatora obszaru danych**<br>_mshr_dataareaid_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: cdm_companyid jednostki cdm_company obcej | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę). |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Łączenie wartości żądania rekrutacyjnego, identyfikatora poziomu wykształcenia i identyfikatora dyscypliny edukacyjnej jako kolejnej metody jednoznacznego identyfikowania rekordu. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
