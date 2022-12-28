---
title: Certyfikat osoby
description: W tym artykule opisano jednostkę Certyfikat osoby dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/15/2022
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
ms.openlocfilehash: 1f9d5a8c83d9714a4d10dec16e66ab87b794b074
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887325"
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
| **Identyfikator typu certyfikatu**<br>mshr_certificatetypeid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne |  Identyfikator typu certyfikatu zdefiniowanego w części Human Resources. |
| **Data rozpoczęcia**<br>mshr_startdate<br>*Data/godzina* | Czytaj/zapisz<br>Wymagane | Data wydania certyfikatu. |
| **Data końcowa**<br>mshr_enddate<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalny | Data wygaśnięcia certyfikatu. |
| **Notatki**<br>mshr_notes<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalnie | Notatki do użytku przez menedżerów zatrudniających i rekruterów. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Wymagane | Identyfikator strony (osoby) kandydata. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Wymagane |  Pole, które ma być używane jako identyfikator rekordu encji. Połączenie numeru strony, identyfikatora typu certyfikatu i daty rozpoczęcia. |
| **Wartość identyfikatora typu certyfikatu**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmcertificatetypeentityid jednostki mshr_hcmcertificatetypeentity | Wygenerowany przez system unikalny identyfikator typu certyfikatu w powiązanej jednostce. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Identyfikator jednostki certyfikatu osoby**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikalny identyfikator dla rekordu jednostki certyfikatu osoby. |




## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
