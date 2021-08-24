---
title: Plan zmiennych wynagrodzeń listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Plan wynagrodzeń zmiennych w Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 96a644bf129de6dd3f78098bcb6415d17058d6decbd7d904a99bb6f050d3a9e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730449"
---
# <a name="payroll-variable-compensation-plan"></a>Plan zmiennych wynagrodzeń listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano encję Plan wynagrodzeń zmiennych dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Ta jednostka udostępnia system zmiennych wynagrodzeń przypisany do danego stanowiska pracownika.

Nazwa fizyczna: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu</br>Potrzebne |Unikalny numer personelu pracownika.  |
| **Data premii**</br>mshr_awarddate</br>*Przesunięcie daty i godziny* | Tylko do odczytu</br>Potrzebne | Data nagrody. |
| **Typ nagrody**</br>mshr_awardtype</br>*[zestaw opcji mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Tylko do odczytu</br>Potrzebne | Rodzaj nagrody zdefiniowanej dla planu wynagrodzeń o zmiennej wysokości. |
| **Waluta**</br>mshr_unitcurrencycode</br>*Ciąg* | Tylko do odczytu </br>Potrzebne |Waluta zdefiniowana dla planu wynagrodzeń o zmiennej wysokości.   |
| **Identyfikator planu stałych wynagrodzeń**</br>mshr_fixedplanid</br>*Ciąg* | Tylko do odczytu | Plan stałych wynagrodzeń, który jest używany jako podstawa do obliczenia nagrody. |
| **Wartość jednostki**</br>mshr_awardamount</br>*Dziesiętny* | Tylko do odczytu | Wartość jednostki |
| **Typ procesu**</br>mshr_processtype</br>*[zestaw opcji mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Tylko do odczytu | Typ procesu. |
| **Typ planu wynagrodzeń o zmiennej wysokości**</br>Ciąg</br>*mshr_typeid* | Tylko do odczytu | Typ planu wynagrodzeń o zmiennej wysokości. |
| **Identyfikator planu wynagrodzeń o zmiennej wysokości**</br>Ciąg</br>*mshr_planid* | Tylko do odczytu | Identyfikator planu wynagrodzeń o zmiennej wysokości. |
| **Pole główne**</br>mshr_primaryfield</br>*GUID* | Tylko do odczytu</br>Wygenerowany przez system. | |
| **Identyfikator pracownika**</br>mshr_fk_employee_id_value</br>*GUID* | Tylko do odczytu</br>Potrzebne</br>Klucz obcy: mshr_Employee_id jednostki mshr_payrollemployeeentity  | Identyfikator pracownika. |
| **Jednostka Planu zmiennych wynagrodzeń listy płac**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Potrzebne</br>Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania planu wynagrodzeń. |


## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Odpowiedź**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
