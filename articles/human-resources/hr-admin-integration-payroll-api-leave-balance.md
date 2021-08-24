---
title: Saldo urlopu
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dla encji saldo urlopu w Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab136e9b40de280387dc3c5207a08a6bb357941feb3a8c736d9671f7850f2bf8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782690"
---
# <a name="leave-balance"></a>Saldo urlopu

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę saldo urlopu dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Jednostka ta podaje saldo urlopów według typu urlopu dla danego pracownika.

Nazwa fizyczna: mshr_essleavebalanceentities.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu | Unikalny numer personelu pracownika. |
| **Bieżące saldo**</br>mshr_balanceavailable</br>*Dziesiętny* | Tylko do odczytu | Aktualne saldo pracownika. |
| **Typ**</br>mshr_balanceavailable</br>*Ciąg* | Tylko do odczytu | Identyfikator typu urlopu. |
| **Stawka naliczania**</br>mshr_accrualratedescription</br> | Tylko do odczytu | Stawka naliczania. |
| **Ostatnia ilość przeniesienia na następny okres**</br>mshr_lastcarryforwardamount</br>*Dziesiętny* | Tylko do odczytu | Ostatnia ilość do przeniesienia. |
| **Wzięte w tym roku**</br>mshr_takenthisyear</br>*Dziesiętny* | Tylko do odczytu | Ilość urlopu w tym roku. |
| **W sumie w tym roku**</br>mshr_totalthisyear</br>*Dziesiętny* | Tylko do odczytu | Całkowita ilość na ten rok. |
| **Identyfikator obszaru danych**</br>mshr_dataareaid_id</br>*Ciąg* | Tylko do odczytu | Określa osobę prawną (firmę). |
| **Pole główne**</br>mshr_primaryfield</br>*GUID* | Tylko do odczytu</br>Wygenerowany przez system | |
| **Identyfikator typu urlopu**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Tylko do odczytu</br>Klucz obcy:mshr_essleavetypeentityid encji mshr_essleavetypeentity  | Identyfikator typu urlopu |
| **Jednostka Saldo urlopu**</br>mshr_essleavebalanceentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania salda. |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Odpowiedź**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
