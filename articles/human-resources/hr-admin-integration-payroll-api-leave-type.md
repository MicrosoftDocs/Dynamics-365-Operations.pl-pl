---
title: Typ urlopu
description: Ten artykuł zawiera szczegółowe informacje i przykładowe zapytanie dla jednostki typu urlopu w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6e7905989df92e943b86f86194c87dcb2a7b1446
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893794"
---
# <a name="leave-type"></a>Typ urlopu


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę typ urlopu dla Dynamics 365 Human Resources.

### <a name="description"></a>Opis

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
