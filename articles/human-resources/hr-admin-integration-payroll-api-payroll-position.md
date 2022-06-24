---
title: Szczegóły listy płac dla stanowisk
description: Ten artykuł zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Szczegóły listy płac dla stanowisk w Dynamics 365 Human Resources.
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
ms.openlocfilehash: ac36b0386312e1631528b8ab5976db2cb3924caf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904138"
---
# <a name="payroll-position"></a>Stanowisko listy płac


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę zadania stanowiska listy płac dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_payrollpositionentity.

### <a name="description"></a>opis

Ta jednostka zawiera informacje dotyczące stanowiska dla danego pracownika.

Nazwa fizyczna: mshr_payrollpositionentity.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | Opis |
| --- | --- | --- |
| **Identyfikator stanowiska**</br>mshr_positionid</br>*Ciąg* | Tylko do odczytu | Identyfikator stanowiska. |
| **Identyfikator cyklu płac**</br>mshr_paycycleid</br>*Ciąg* | Tylko do odczytu | Zdefiniowano cykl płac dla stanowiska. |
| **Zwykłe godziny (rocznie)**</br>annualregularhours</br>*Liczba dziesiętna* | Tylko do odczytu | Roczne godziny pracy ustalone na stanowisku. |
| **Zapłacone przez firmę**</br>paidbylegalentity</br>*Ciąg* | Tylko do odczytu | Firma zdefiniowana dla stanowiska odpowiedzialnego za wydawanie płatności. |
| **Data ważności**</br>validto</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data, do której obowiązują szczegóły dotyczące stanowiska. |
| **Data wejścia w życie**</br>validfrom</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data, od której obowiązują szczegóły dotyczące stanowiska. |
| **Pole główne**</br>mshr_primaryfield</br>*Ciąg* | Wygenerowany przez system | Pole główne. |
| **Identyfikator podmiotu zawierający szczegóły dotyczące stanowiska płacowego**</br>payrollpositiondetailsentityid</br>*Guid* | Potrzebne</br>Wygenerowany przez system. | Wygenerowana przez system wartość unikatowego globalnego identyfikatora (GUID) umożliwiająca jednoznaczną identyfikację stanowiska. |

## <a name="relations"></a>Relacje

| Wartości właściwości | Encja powiązana | Właściwość nawigacji | Typ kolekcji |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | Nie dotyczy |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | Nie dotyczy |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Odpowiedź**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
