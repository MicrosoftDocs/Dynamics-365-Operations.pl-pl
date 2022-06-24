---
title: Certyfikat osoby
description: W tym artykule opisano jednostkę Certyfikat osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: a3c3be061cb8a18a19729932352c82ff3b787000
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897930"
---
# <a name="person-certificate"></a>Certyfikat osoby


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Certyfikat osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersoncertificateentity

## <a name="description"></a>opis

Ta jednostka opisuje certyfikaty zawodowe kandydata.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki certyfikatu osoby**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikalny identyfikator dla rekordu jednostki certyfikatu osoby. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator strony (osoby) kandydata. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Identyfikator typu certyfikatu**<br>mshr_certificatetypeid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne |  Identyfikator typu certyfikatu zdefiniowanego w części Human Resources. |
| **Wartość identyfikatora typu certyfikatu**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmcertificatetypeentityid jednostki mshr_hcmcertificatetypeentity | Wygenerowany przez system unikalny identyfikator typu certyfikatu w powiązanej jednostce. |
| **Data rozpoczęcia**<br>mshr_startdate<br>*Data/godzina* | Czytaj/zapisz<br>Potrzebne | Data wydania certyfikatu. |
| **Data końcowa**<br>mshr_enddate<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalny | Data wygaśnięcia certyfikatu. |
| **Notatki**<br>mshr_notes<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Notatki do użytku przez menedżerów zatrudniających i rekruterów. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |  Pole, które ma być używane jako identyfikator rekordu encji. Połączenie numeru strony, identyfikatora typu certyfikatu i daty rozpoczęcia. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
