---
title: Zadanie stanowiska listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Stanowisko pracy na liście płac w Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 842c459acd8b5e1a8b6074243b3afa18dc6a13c5
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314244"
---
# <a name="payroll-position-job"></a>Zadanie stanowiska listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano podmiot zadania pozycji listy płac dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Podmiot ten określa związek pomiędzy stanowiskiem a pracą dla danego stałego planu wynagrodzeń.

Nazwa fizyczna: mshr_payrollpositionjobentity.

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator stanowiska**<br>mshr_jobid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |Identyfikator zadania. |
| **Data wejścia w życie**<br>mshr_validto<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data, od której obowiązuje stanowisko i stosunek pracy. |
| **Data ważności**<br>mshr_validto<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data obowiązywania stanowiska i stosunku pracy.  |
| **Identyfikator stanowiska**<br>mshr_positionid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Identyfikator stanowiska. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Potrzebne<br>Wygenerowany przez system |  |
| **Wartość identyfikatora zadania stanowiska**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_PayrollPositionJobEntity klucza mshr_payrollpositionjobentity |identyfikator stanowiska związany ze stanowiskiem.|
| **Wartość identyfikatora stałego planu wynagrodzeń**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_FixedCompPlan_id dla mshr_payrollfixedcompensationplanentity  | Identyfikator planu stałych wynagrodzeń powiązany ze stanowiskiem. |
| **Identyfikator jednostki stanowiska na liście płac**<br>mshr_payrollpositionjobentityid<br>*Guid* | Potrzebne<br>Wygenerowany przez system. | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania zadania.  |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Odpowiedź**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
