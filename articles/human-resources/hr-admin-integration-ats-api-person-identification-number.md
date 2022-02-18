---
title: Numer dokumentu identyfikacyjnego osoby
description: W tym temacie opisano jednostkę Numer dokumentu identyfikacyjnego osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0991f5b2e17e64e23f78b346c451f7c43bc20378
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067158"
---
# <a name="person-identification-number"></a>Numer dokumentu identyfikacyjnego osoby


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Numer dokumentu identyfikacyjnego osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>opis

Podmiot ten opisuje numery identyfikacyjne kandydata. Umożliwia konsumentowi API zapisywanie numerów identyfikacyjnych, takich jak numery PESEL lub numery paszportów, w aktach kandydata. Numery identyfikacyjne znajdują się w aktach pracownika, ale nie w aktach kandydatów. Aplikacja integrująca może zapisywać wartości w bazie danych Human Resources, ale liczby nie będą widoczne w dziale kadr, dopóki nie zostanie utworzony rekord pracownika kandydata.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Numer identyfikacyjny osoby Identyfikator jednostki**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Niepowtarzalny identyfikator podstawowy dla rekordu numeru identyfikacyjnego osoby. |
| **Typ wpisu**<br>mshr_entrytype<br>*Ciąg* | Czytaj-zapisz<br>Opcjonalny | Dowolna wartość wskazująca rodzaj wpisu numeru identyfikacyjnego. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj-zapisz<br>Opcjonalny | Opis numeru identyfikacyjnego. |
| **Data ważności**<br>mshr_expirationdate<br>*Data/godzina* | Czytaj-zapisz<br>Opcjonalny | Data wygaśnięcia numeru identyfikacyjnego lub skojarzonego dokumentu. |
| **Główne**<br>mshr_isprimary<br>*zestaw opcji mshr_noyes* | Czytaj-zapisz<br>Opcjonalny | Określa, czy numer identyfikacyjny jest podstawowym rekordem osoby dla tego typu identyfikacji. |
| **Numer identyfikacyjny**<br>mshr_identificationnumber<br>*Ciąg* | Czytaj-zapisz<br>Potrzebne | Numer identyfikacyjny. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj-zapisz<br>Potrzebne | Identyfikator strony (osoby) posiadającej numer identyfikacyjny. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Unikalny identyfikator strony (osoby). |
| **Identyfikator typu identyfikacji**<br>mshr_identificationtypeid<br>*Ciąg* | Czytaj-zapisz<br>Potrzebne | Rodzaj numeru identyfikacyjnego. |
| **Wartość identyfikacyjna typu identyfikatora**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmidentificationtypeentityid jednostki mshr_hcmidentificationtypeentity | Wygenerowany przez system unikalny identyfikator dla typu identyfikacji. |
| **Numer identyfikacyjny Agencji wystawiającej**<br>mshr_issuingagencyid<br>*Ciąg* | Czytaj-zapisz<br>Opcjonalny | Agencja lub organizacja wystawiające numer identyfikacyjny. |
| **Wartość numeru identyfikacyjnego Agencji wystawiającej**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmissuingagencyentityid jednostki mshr_hcmissuingagencyentity | Wygenerowany przez system niepowtarzalny identyfikator agencji wydającej numer identyfikacyjny. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole, które ma być używane jako identyfikator rekordu encji. Połączenie numeru strony, identyfikatora typu identyfikatora i numeru identyfikacyjnego. |
| **Data wystawienia**<br>mshr_issuedate<br>*Data* | Czytaj-zapisz<br>Opcjonalny | Data nadania numeru identyfikacyjnego. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
