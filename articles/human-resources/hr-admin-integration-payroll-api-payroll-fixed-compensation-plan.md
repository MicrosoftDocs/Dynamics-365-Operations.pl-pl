---
title: Plan stałych wynagrodzeń listy płac
description: Ten artykuł zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Płace stałe plany wynagrodzeń w Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: 83fa8aeb38cc44191242cf029022939cefb22cb8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909854"
---
# <a name="payroll-fixed-compensation-plan"></a>Plan stałych wynagrodzeń listy płac


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Plan wynagrodzeń stałych dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Ta jednostka udostępnia system stałych wynagrodzeń przypisany do danego stanowiska pracownika.

Nazwa fizyczna: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator planu**</br>mshr_planid</br>*Ciąg* | Tylko do odczytu | Określa plan wynagrodzeń.  |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu | Unikalny numer personelu pracownika. |
| **Stawka płacy**</br>mshr_payrate</br>*Dziesiętny* | Tylko do odczytu | Stawka płacy zdefiniowana w planie stałych wynagrodzeń. |
| **Identyfikator stanowiska**</br>mshr_positionid</br>*Ciąg* | Tylko do odczytu | Identyfikator stanowiska powiązany z rejestracją pracownika i planu stałych wynagrodzeń. |
| **Data wejścia w życie**</br>mshr_validfrom</br>*Przesunięcie daty i godziny* |  Tylko do odczytu | Data, od której obowiązuje stałe wynagrodzenie pracownika.  |
| **Data ważności**</br>mshr_validto</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data, do której obowiązuje stałe wynagrodzenie pracownika. |
| **Częstotliwość wypłat**</br>mshr_payfrequency</br>*Ciąg* | Tylko do odczytu | Identyfikator [częstotliwości wypłat wynagrodzenia](hr-admin-integration-payroll-api-compensation-pay-frequency.md) dla danej stawki płacy. |
| **Waluta**</br>mshr_currency</br>*Ciąg* | Tylko do odczytu | Waluta zdefiniowana dla stałego planu wynagrodzeń. |
| **Jednostka Plan stałych wynagrodzeń listy płac**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania planu wynagrodzeń. |

## <a name="relations"></a>Relacje

|Wartości właściwości | Encja powiązana | Właściwość nawigacji | Typ kolekcji |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Odpowiedź**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
