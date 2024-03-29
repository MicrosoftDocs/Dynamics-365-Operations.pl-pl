---
title: Kwalifikacje osoby
description: W tym artykule opisano jednostkę Kwalifikacje osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 713fde6d05904f96f7b17721e15805e07159cf78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891329"
---
# <a name="person-skill"></a>Kwalifikacje osoby


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Kwalifikacje osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersonskillentity

## <a name="description"></a>opis

Ta jednostka opisuje umiejętności kandydata.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki Kwalifikacje osoby**<br>mshr_hcmpersonskillentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikatowy identyfikator rekordu jednostki. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne |   Identyfikator skojarzonego rekordu strony (osoby). |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Osoba poświadczająca**<br>mshr_certifier<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer pracownika, który poświadczył tę umiejętność. |
| **Wartość identyfikatora osoby poświadczającej**<br>_mshr_fk_certifier_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmworkerentityid jednostki mshr_hcmworkerentity | Wygenerowany przez system unikalny identyfikator rekordu pracownika dla pracownika, który poświadczył umiejętność. |
| **Identyfikator kwalifikacji**<br>mshr_skillid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator umiejętności zdefiniowanej w części Human Resources. |
| **Wartość identyfikatora kwalifikacji**<br>_mshr_fk_skill_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmskillentityid jednostki mshr_hcmskillentity | Wygenerowany przez system identyfikator wybranej umiejętności. |
| **Lata doświadczenia**<br>mshr_yearsofexperience<br>*Dziesiętny* | Czytaj/zapisz<br>Opcjonalny | Lata doświadczenia kandydata w tych kwalifikacjach. |
| **Identyfikator oceny**<br>mshr_ratingid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Typ skali oceny. Dla tej jednostki wartością są **Kwalifikacje**. |
| **Typ poziomu**<br>mshr_leveltype<br>*zestaw opcji mshr_hrmskillleveltype* | Czytaj/zapisz<br>Potrzebne | Typ kategoryzacji dla poziomu przypisanego do umiejętności. |
| **Identyfikator poziomu**<br>mshr_levelid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator poziomu oceniania, który kandydat ma dla tej umiejętności. |
| **Wartość identyfikatora poziomu oceny**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmratinglevelentityid jednostki mshr_hcmratinglevelentity | Wygenerowany przez system identyfikator poziomu ratingu. |
| **Data poziomu**<br>mshr_leveldate<br>*Data/godzina* | Czytaj/zapisz<br>Potrzebne | Data oceny kandydata za kwalifikacje. |
| **Egzaminator poziomu**<br>mshr_ratinglevelexaminer<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Liczba pracowników, którzy ocenili kandydata. |
| **Wartość identyfikatora egzaminatora poziomu oceny**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmworkerentityid jednostki mshr_hcmworkerentity | Wygenerowany przez system identyfikator pracownika, który sprawdzał poziom umiejętności kandydata. |
| **Zweryfikowano**<br>mshr_verified<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Wskazuje, czy oceniany poziom umiejętności został zweryfikowany. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole, które ma być używane jako identyfikator rekordu encji. Kombinacja numeru strony, typu poziomu, identyfikatora umiejętności i daty poziomu. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
