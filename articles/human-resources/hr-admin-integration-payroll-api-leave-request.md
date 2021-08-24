---
title: Wniosek urlopowy
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dla encji wniosku urlopowego w Dynamics 365 Human Resources.
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
ms.openlocfilehash: c6c772c26e8a789a54c9eeb36c1cab576a7f94cb3ede547db46fe18a2e89c8ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762029"
---
# <a name="leave-request"></a>Wniosek urlopowy

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Wniosku o urlop dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Ta jednostka zawiera informacje dotyczące wniosku urlopowego.

Nazwa fizyczna: mshr_essleaverequestentity.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator wniosku**</br>mshr_requestid</br>*Ciąg* | Tylko do odczytu | Identyfikator wniosku. |
| **Identyfikator typu urlopu**</br>mshr_leavetypeid</br>*Ciąg* | Tylko do odczytu | Identyfikator typu urlopu. |
| **Data**</br>mshr_leavedate</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data wniosku urlopowego. |
| **Ilość**</br>mshr_amount</br>*Dziesiętny* | Tylko do odczytu | Kwota wniosku urlopowego. |
| **Typ pół dnia**</br>mshr_halfdaydefinition</br>*zestaw opcji mshr_LeaveHalfDayDefinition* | Tylko do odczytu | Typ półdniowego urlopu. |
| **Komentarz**</br>mshr_comment</br>*Ciąg* | Tylko do odczytu | Komentarz do wniosku. |
| **Stan**</br>mshr_status</br>*zestaw opcji mshr_status* | Tylko do odczytu | Stan żądania. |
| **Data**</br>mshr_requestdate</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data wniosku. |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu | Unikalny numer personelu pracownika. |
| **Identyfikator kodu przyczyny**</br>mshr_reasoncodeid</br>*Ciąg* | Tylko do odczytu | Identyfikator kodu przyczyny. |
| **Identyfikator obszaru danych**</br>mshr_dataareaid</br>*Ciąg* | Tylko do odczytu | Określa osobę prawną (firmę). |
| **Pole główne**</br>mshr_primaryfield</br>*GUID* | Tylko do odczytu</br>Wygenerowany przez system | |
| **Jednostka Typ urlopu**</br>mshr_essleaverequestentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania wniosku o urlop. |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Odpowiedź**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
