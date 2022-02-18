---
title: Umiejętność we wniosku o rekrutację
description: W tym temacie opisano jednostkę Umiejętność we wniosku o rekrutację dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 245b9a1ff4f140b9288b79c70820204f3082568b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068616"
---
# <a name="recruiting-request-skill"></a>Umiejętność we wniosku o rekrutację


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Umiejętność we wniosku o rekrutację dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>opis

Opisuje wymagania dotyczące kwalifikacji dla questu RecruitingRequest.

### <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki Umiejętności we wniosku o rekrutację**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikalny identyfikator rekordu **Umiejętności we wniosku rekrutacji**. |
| **Identyfikator wniosku o rekrutację**<br>mshr_recruitingrequestid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Odczytywalny przez użytkownika unikatowy identyfikator powiązanego wniosku o rekrutację. |
| **Wartość identyfikatora wniosku o rekrutację**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br> Klucz obcy: mshr_hcmrecruitingrequestentityid należący do jednostki mshr_hcmrecruitingrequestentity | Wygenerowany przez system unikalny identyfikator powiązanego wniosku rekrutacyjnego. |
| **Identyfikator kwalifikacji**<br>mshr_skillid<br>*Ciąg*<br> | Odpisz raz<br>Potrzebne | Odczytywalny przez użytkownika unikatowy identyfikator wymaganej umiejętności. |
| **Wartość identyfikatora kwalifikacji**<br>_mshr_fk_skill_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmskillentityid jednostki mshr_hcmskillentity | Wygenerowany przez system unikalny identyfikator wymaganej umiejętności. |
| **Identyfikator poziomu oceny**<br>mshr_ratinglevelid<br>*Ciąg* | Odpisz raz<br>Opcjonalny | Wymagana wartość poziomu umiejętności wybrana dla stanowiska na podstawie modelu oceniania przypisanego do umiejętności. |
| **Wartość identyfikatora poziomu oceny**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmratinglevelentityid jednostki mshr_hcmratinglevelentity | Wygenerowany przez system unikatowy identyfikator poziomu. |
| **Opis kwalifikacji**<br>mshr_skilldescription<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Opis kwalifikacji. |
| **Opis poziomu oceniania**<br>mshr_ratingleveldescription<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Opis wybranego poziomu umiejętności. |
| **Identyfikator obszaru danych**<br>mshr_dataareaid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Określa osobę prawną (firmę). |
| **Wartość identyfikatora obszaru danych**<br>_mshr_dataareaid_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: cdm_companyid jednostki cdm_company obcej | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę). |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Łączenie wartości żądania rekrutacji i identyfikatora umiejętności jako kolejna metoda unikalnej identyfikacji rekordu. |
| **Identyfikator modelu oceny**<br>mshr_ratingmodelid<br>*Ciąg* | Czytaj-zapisz<br>Potrzebne | Model oceniania używany do oceniania umiejętności. |
| **Wartość identyfikatora modelu oceny**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmratingmodelentityid jednostki mshr_hcmratingmodelentity | Wygenerowany przez system niepowtarzalny identyfikator modelu oceny używanego do oceny umiejętności. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
