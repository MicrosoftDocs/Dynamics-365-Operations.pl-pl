---
title: Typ urlopu
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dla encji typu urlopu w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5e64b533ad7be23060701e8826a25736a078b59d1ecf824bee0e2dd05c9c78f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713109"
---
# <a name="leave-type"></a>Typ urlopu

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę typ urlopu dla Dynamics 365 Human Resources.

### <a name="description"></a>opis

Ten element dostarcza informacji dla danego typu urlopu.

Nazwa fizyczna: mshr_essleavetypeentity.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator typu urlopu**</br>mshr_leavetypeid</br>*Ciąg* | Tylko do odczytu | Identyfikator typu urlopu. |
| **Opis**</br>mshr_description</br>*Ciąg* | Tylko do odczytu | Opis typu urlopu. |
| **Kategoria**</br>mshr_category</br>*zestaw opcji mshr_LeaveTypeCategory* | Tylko do odczytu | Kategoria typu urlopu. |
| **Wymagany kod przyczyny**</br>mshr_isreasoncoderequired</br>*zestaw opcji mshr_NoYes* | Tylko do odczytu | Określa, czy dla typu urlopu jest wymagany kod przyczyny. |
| **Jednostka urlopu**</br>mshr_leaveamountunit</br>*zestaw opcji mshr_LeaveAmountUnit* | Tylko do odczytu | Część tego typu urlopu. |
| **Włącz pół dnia**</br>mshr_enablehalfdaydefinition</br>*zestaw opcji mshr_NoYes* | Określa, czy dla typu urlopu włączono pół dnia. |
| **Identyfikator obszaru danych**</br>mshr_dataareaid_id</br>*Ciąg* | Tylko do odczytu | Określa osobę prawną (firmę). |
| **Jednostka Typ urlopu**</br>mshr_essleavetypeentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania typu urlopu. |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Odpowiedź**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
