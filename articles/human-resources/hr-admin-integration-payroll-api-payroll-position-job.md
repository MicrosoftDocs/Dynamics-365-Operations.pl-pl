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
ms.openlocfilehash: 349479d9e77861b54d879bcfd93f7af0e38cff95
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069839"
---
# <a name="payroll-position-job"></a>Zadanie stanowiska listy płac


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano podmiot zadania pozycji listy płac dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Podmiot ten określa związek pomiędzy stanowiskiem a pracą dla danego stałego planu wynagrodzeń.

Nazwa fizyczna: mshr_payrollpositionjobentity.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | Opis |
| --- | --- | --- |
| **Identyfikator stanowiska**</br>mshr_positionid</br>*Ciąg* | Tylko do odczytu | Identyfikator stanowiska. |
| **Data wejścia w życie**</br>mshr_validto</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data, od której ważne jest stanowisko i stosunek pracy. |
| **Data ważności**</br>mshr_validto</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data ważności stanowiska i stosunku pracy. |
| **Identyfikator stanowiska**</br>mshr_jobid</br>*Ciąg* | Tylko do odczytu | Identyfikator zadania. |
| **Pole główne**</br>mshr_primaryfield</br>*Ciąg* | Wygenerowany przez system | Pole główne. |
| **Identyfikator jednostki stanowiska na liście płac**</br>mshr_payrollpositionjobentityid</br>*Guid* | Wygenerowany przez system. | Wygenerowana przez system wartość unikatowego globalnego identyfikatora (GUID) umożliwiająca jednoznaczną identyfikację pracy. |

## <a name="relations"></a>Relacje

| Wartości właściwości | Encja powiązana | Właściwość nawigacji | Typ kolekcji |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | Nie dotyczy |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

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
