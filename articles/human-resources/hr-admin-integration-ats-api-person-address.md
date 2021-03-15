---
title: Adres osoby
description: W tym temacie opisano jednostkę Adres osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 9911362ff8260860864cfe24f0b60f59adb77186
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125889"
---
# <a name="person-address"></a>Adres osoby

W tym temacie opisano jednostkę Adres osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersonaddressentities

## <a name="description"></a>opis

Ta jednostka zawiera listę adresów pocztowych rekordów kandydatów.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki Adres osoby**<br>mshr_hcmpersonaddressentityid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikatowy identyfikator rekordu jednostki. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator skojarzonego rekordu strony (osoby). |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system identyfikator rekordu jednostki strony (osoby). |
| **Identyfikator lokalizacji**<br>mshr_locationid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Identyfikator lokalizacji rekordu adresu. Ustaw wartości w jednostce mshr_logisticspostaladdresslocationcdsentity. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opis adresu kandydata. |
| **Role**<br>mshr_roles<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Role przypisane dla tego adresu. Można przypisać więcej niż jedną rolę. Każda rola powinna być oddzielona średnikiem. Prawidłowe wartości zawarte w jednostce mshr_logisticslocationroleentity. |
| **Ulica**<br>mshr_street<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer budynku. |
| **Miasto**<br>mshr_city<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Miasto w adresie. Ustaw w jednostce mshr_logisticsaddresscityentity. |
| **Stanowy**<br>mshr_state<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Województwo w adresie. Ustaw w jednostce mshr_logisticsaddressstateentity. |
| **Powiat**<br>mshr_county<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Powiat w adresie. Ustaw w jednostce mshr_logisticsaddresscountyentity. |
| **Kod pocztowy**<br>mshr_zipcode<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kod pocztowy w adresie. Ustaw w jednostce mshr_logisticsaddresspostalcodeentity. |
| **Identyfikator regionu kraju**<br>mshr_countryregionid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kraj lub region w adresie. |
| **Wartość identyfikatora regionu kraju**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_logisticaddresscountryregionentityid jednostki mshr_logisticsaddresscountryregionentity | Wygenerowany przez system unikalny identyfikator kraju / regionu adresu. |
| **Główne**<br>mshr_isprimary<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Określa, czy ten adres jest adresem podstawowym osoby w określonej roli. |
| **Jest prywatny**<br>mshr_isprivate<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Potrzebne | Określa, czy ten adres jest adresem prywatnym danej osoby. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole używane jako podstawowy identyfikator rekordu jednostki. Kombinacja numeru strony i identyfikatora lokalizacji. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]