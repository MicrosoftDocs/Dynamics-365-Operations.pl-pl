---
title: Plan stałych wynagrodzeń listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Płace stałe plany wynagrodzeń w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 24f8af4d691c3085c36018c574fa3b917a3d6953
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314220"
---
# <a name="payroll-fixed-compensation-plan"></a>Plan stałych wynagrodzeń listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano encję Plan wynagrodzeń stałych dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Ta jednostka udostępnia system stałych wynagrodzeń przypisany do danego stanowiska pracownika.

Nazwa fizyczna: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator pracownika**<br>mshr_fk_employee_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_Employee_id jednostki mshr_payrollemployeeentity  | Identyfikator pracownika |
| **Stawka płacy**<br>mshr_payrate<br>*Dziesiętny* | Tylko do odczytu<br>Potrzebne | Stawka płacy zdefiniowana w planie stałych wynagrodzeń. |
| **Identyfikator planu**<br>mshr_planid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |Określa plan wynagrodzeń.  |
| **Data wejścia w życie**<br>mshr_validfrom<br>*Przesunięcie daty i godziny* |  Tylko do odczytu<br>Potrzebne |Data, od której obowiązuje stałe wynagrodzenie pracownika.  |
| **Jednostka Plan stałych wynagrodzeń listy płac**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Potrzebne<br>Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania planu wynagrodzeń. |
| **Częstotliwość wypłat**<br>mshr_payfrequency<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |Częstotliwość wypłat dla pracownika.  |
| **Data ważności**<br>mshr_validto<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data, do której obowiązuje stałe wynagrodzenie pracownika. |
| **Identyfikator stanowiska**<br>mshr_positionid<br>*Ciąg* | Tylko do odczytu <br>Potrzebne | Identyfikator stanowiska powiązany z rejestracją pracownika i planu stałych wynagrodzeń. |
| **Waluta**<br>mshr_currency<br>*Ciąg* | Tylko do odczytu <br>Potrzebne |Waluta zdefiniowana dla stałego planu wynagrodzeń   |
| **Numer pracownika**<br>mshr_personnelnumber<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |Unikalny numer personelu pracownika.  |

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
