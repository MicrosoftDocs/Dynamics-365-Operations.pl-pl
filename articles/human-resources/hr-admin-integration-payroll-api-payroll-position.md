---
title: Szczegóły listy płac dla stanowisk
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki Szczegóły listy płac dla stanowisk w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 05e9d6441cf99dce3f4663b9d5ba57e2b386e8c2f3060f75550270083f3b98b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741460"
---
# <a name="payroll-position"></a>Stanowisko listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano encję zadania stanowiska listy płac dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_payrollpositionentity.

### <a name="description"></a>opis

Ta jednostka zawiera informacje dotyczące stanowiska dla danego pracownika.

Nazwa fizyczna: 

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Zwykłe godziny (rocznie)**<br>annualregularhours<br>*Dziesiętny* | Tylko do odczytu<br>Potrzebne | Zwykłe godziny (rocznie) zdefiniowane dla stanowiska.  |
| **Identyfikator podmiotu zawierający szczegóły dotyczące stanowiska płacowego**<br>payrollpositiondetailsentityid<br>*Guid* | Potrzebne<br>Wygenerowany przez system. | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania stanowiska.  |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Potrzebne<br>Wygenerowany przez system |  |
| **Wartość identyfikatora zadania stanowiska**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_PayrollPositionJobEntity klucza mshr_payrollpositionjobentity |identyfikator stanowiska związany ze stanowiskiem.|
| **Wartość identyfikatora stałego planu wynagrodzeń**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_FixedCompPlan_id dla mshr_payrollfixedcompensationplanentity  | Identyfikator planu stałych wynagrodzeń powiązany ze stanowiskiem. |
| **Identyfikator cyklu płac**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Zdefiniowano cykl płac dla stanowiska. |
| **Zapłacone przez firmę**<br>paidbylegalentity<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Firma zdefiniowana dla stanowiska odpowiedzialnego za wydawanie płatności. |
| **Identyfikator stanowiska**<br>mshr_positionid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Identyfikator stanowiska. |
| **Data ważności**<br>validto<br>*Przesunięcie daty i godziny* | Tylko do odczytu<br>Potrzebne |Data, od której obowiązują szczegóły dotyczące stanowiska.  |
| **Data wejścia w życie**<br>validfrom<br>*Przesunięcie daty i godziny* | Tylko do odczytu<br>Potrzebne |Data, do której obowiązują szczegóły dotyczące stanowiska.  |

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
