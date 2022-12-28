---
title: Kontrola osoby
description: W tym artykule opisano jednostkę Kontrola osoby dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3c316e0381f4d407ed7c4c39b5949717b71477bd
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831898"
---
# <a name="person-screening"></a>Kontrola osoby


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Kontrola osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersonscreeningentity

## <a name="description"></a>opis

Ta jednostka opisuje kontrole, które kandydat przeszedł lub musi przejść w celu zatrudnienia.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "_mshr_fk_screeningtype_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Notatki**<br>mshr_note<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalnie | Notatki do użytku przez menedżerów zatrudniających i rekruterów. |
| **Wymagane przed datą**<br>mshr_requiredby<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalnie | Data, do której kontrola musi zostać zakończona. |
| **Stan**<br>mshr_status<br>*zestaw opcji mshr_hcmcompletionstatus*|Czytaj/zapisz<br>Wymagane | Dostarcza stan kandydata do kontroli. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Wymagane | Numer strony (osoby) skojarzony z kandydatem. |
| **Identyfikator typu kontroli**<br>mshr_screeningtypeid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne<br>Klucz obcy: ScreeningType | Identyfikator typu kontroli zdefiniowanego w części Human Resources. |
| **Wartość identyfikatora jednostki typu kontroli**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmscreeningtypeentityid jednostki mshr_hcmscreeningtypeentity | Wygenerowany przez system identyfikator rekordu typu kontroli w skojarzonej jednostce. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* |  Tylko do odczytu<br>Wymagane | Pole, które ma być używane jako identyfikator rekordu encji. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Identyfikator jednostki kontroli osoby**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system| Unikalny identyfikator podstawowy dla rekordu kontroli osoby. |
| **Data zakończenia**<br>mshr_completeddate<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalnie | Data zakończenia kontroli. |


## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
