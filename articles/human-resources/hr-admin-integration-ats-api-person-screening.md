---
title: Kontrola osoby
description: W tym temacie opisano jednostkę Kontroli osoby dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
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
ms.openlocfilehash: 241b9888624d95bf37a82b6e9b807509818387d2d4f4e5eac67bd67afdaed735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782786"
---
# <a name="person-screening"></a>Kontrola osoby

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Kontroli osoby dla Dynamics 365 Human Resources.

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
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki kontroli osoby**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Unikalny identyfikator podstawowy dla rekordu kontroli osoby. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Numer strony (osoby) skojarzony z kandydatem. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Identyfikator typu kontroli**<br>mshr_screeningtypeid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne<br>Klucz obcy: ScreeningType | Identyfikator typu kontroli zdefiniowanego w części Human Resources. |
| **Wartość identyfikatora jednostki typu kontroli**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmscreeningtypeentityid jednostki mshr_hcmscreeningtypeentity | Wygenerowany przez system identyfikator rekordu typu kontroli w skojarzonej jednostce. |
| **Wymagane przed datą**<br>mshr_requiredby<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalny | Data, do której kontrola musi zostać zakończona. |
| **Stan**<br>mshr_status<br>*zestaw opcji mshr_hcmcompletionstatus*<br>Czytaj/zapisz<br>Potrzebne | Dostarcza stan kandydata do kontroli. |
| **Data zakończenia**<br>mshr_completeddate<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalny | Data zakończenia kontroli. |
| **Notatki**<br>mshr_note<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Notatki do użytku przez menedżerów zatrudniających i rekruterów. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]