---
title: Pracownik etatowy listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Pracownik etatowy na liście płac w Dynamics 365 Human Resources.
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
ms.openlocfilehash: e853a8a5730d397f253c8ce3a330794594dfd907
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068491"
---
# <a name="payroll-employee"></a>Pracownik etatowy listy płac


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano encję Pracownik listy płac dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_payrollemployeeentity.

### <a name="description"></a>opis

Ta jednostka zawiera informacje o pracowniku. Musisz ustawić [parametry integracji listy płac](hr-admin-integration-payroll-api-parameters.md) przed użyciem tej jednostki.

>[!IMPORTANT] 
>Pola **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** i **NameValidTo** nie będą już dostępne w tej encji. Zapewnia to, że istnieje tylko jedno źródło danych daty efektywnej, które wspiera tę jednostkę.
>Te pola będą dostępne w **DirPersonNameHistoricalEntity**, który został wydany w aktualizacji platformy 43. Istnieje relacja OData z encji **PayrollEmployeeEntity** do encji **DirPersonNameHistoricalEntity**. 

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator firmy**</br>mshr_legalentityid</br>*Ciąg* | Tylko do odczytu | Określa osobę prawną (firmę). |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu | Unikalny numer personelu pracownika. |
| **Data rozpoczęcia zatrudnienia**</br>mshr_employmentstartdate</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data rozpoczęcia zatrudnienia pracownika. |
| **Data zakończenia zatrudnienia**</br>mshr_employmentenddate</br>*Przesunięcie daty i godziny* | Tylko do odczytu |Data zakończenia zatrudnienia pracownika.  |
| **Data urodzenia**</br>mshr_birthdate</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data urodzenia pracownika. |
| **Rodzaj**</br>mshr_gender</br>[zestaw opcji mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Tylko do odczytu | Płeć pracownika. |
| **Typ zatrudnienia**</br>mshr_employmenttype</br>[zestaw opcji mshr_hcmemploymenttype](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Tylko do odczytu | Typ zatrudnienia. |
| **Identyfikator typu identyfikacji**</br>mshr_identificationtypeid</br>*Ciąg* |Tylko do odczytu | Typ identyfikacji zdefiniowany dla pracownika. |
| **Numer identyfikacyjn do**</br>mshr_identificationnumber</br>*Ciąg* | Tylko do odczytu |Numer identyfikacji zdefiniowany dla pracownika. |
| **Gotowe do wypłaty**</br>mshr_readytopay</br>[zestaw opcji mshr_noyes](hr-admin-integration-payroll-api-no-yes.md) | Tylko do odczytu | Wskazuje, czy pracownik etatowy jest oznaczony jako gotowy do otrzymania zapłaty. |
| **Identyfikator jednostki Pracownik listy płac**</br>mshr_payrollemployeeentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość unikatowego globalnego identyfikatora (GUID) umożliwiająca jednoznaczną identyfikację pracownika. |

## <a name="relations"></a>Relacje

|Wartości właściwości | Encja powiązana | Właściwość nawigacji | Typ kolekcji |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Przykładowa kwerenda dla pracownika na liście płac

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**Odpowiedź**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
