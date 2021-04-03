---
title: Osoba kontaktowa strony
description: W tym temacie opisano jednostkę Osoby kontaktowej strony dla Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f5a942ef93af4348404c74d8b15d98ae6fa796ff
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466743"
---
# <a name="party-contact"></a>Osoba kontaktowa strony

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Osoby kontaktowej strony dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_dirpartycontactentities

## <a name="description"></a>opis

Jednostka ten opisuje dane kontaktowe kandydata, w tym telefon, e-mail i konta w mediach społecznościowych.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki kontaktu strony**<br>mshr_dirpartycontactentityid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikatowy identyfikator rekordu jednostki. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator skojarzonego rekordu strony (osoby). |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Identyfikator lokalizacji**<br>mshr_locationid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator lokalizacji rekordu adresu. Ustaw wartości w jednostce mshr_logisticspostaladdresslocationcdsentity. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opis szczegółów kontaktu. |
| **Typ**<br>mshr_type<br>*zestaw opcji mshr_logisticselectronicaddressmethodtype* | Czytaj/zapisz<br>Potrzebne | Typ szczegółów kontaktu. |
| **Kod kraju / regionu**<br>mshr_countryregioncode<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kraj lub region w adresie. |
| **Lokalizator**<br>mshr_locator<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Dane kontaktowe. Na przykład jeśli typem jest **Adres e-mail**, to pole zawiera adres e-mail kandydata. |
| **Rozszerzenie lokalizatora**<br>mshr_locatorextension<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Rozszerzenie lokalizatora. Na przykład, jeśli typem jest **Telefon**, ta właściwość zawiera rozszerzenie numeru telefonu. |
| **Jest urządzeniem przenośnym**<br>mshr_ismobile<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Określa, czy telefon jest numerem telefonu komórkowego. |
| **Jest komunikatem błyskawicznym**<br>mshr_isinstantmessage<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Określa, czy telefon jest włączony dla wiadomości błyskawicznych. |
| **Główne**<br>mshr_isprimary<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Określa główny kontakt typu kontaktu. Dla każdego typu kontaktu może istnieć tylko jeden rekord główny. |
| **Jest prywatny**<br>mshr_isprivate<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Określa, czy ten adres jest adresem prywatnym danej osoby. |
| **Cel**<br>mshr_purpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel/rola danych kontaktowych. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole używane jako podstawowy identyfikator rekordu jednostki. Kombinacja numeru strony, typu, opisu i lokalizatora. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]