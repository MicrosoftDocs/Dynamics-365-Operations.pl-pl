---
title: Poziom oceniania
description: W tym temacie opisano jednostkę Poziom oceniania dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dbdbea7087d8bca8563da10d1bf9a97df24e8b3
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464749"
---
# <a name="rating-level"></a>Poziom oceniania

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Poziom oceniania dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmratinglevelentity

## <a name="description"></a>opis

Ta jednostka udostępnia dostępne poziomy oceniania kwalifikacji. Poziomy oceniania obowiązują dla wszystkich firm.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki na poziomie oceny**<br>mshr_hcmratinglevelentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Wygenerowany przez system unikatowy identyfikator poziomu. |
| **Identyfikator poziomu oceny**<br>mshr_ratinglevelid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Czytelny dla użytkownika unikalny identyfikator poziomu. |
| **Identyfikator modelu oceny**<br>mshr_ratingmodelid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Model oceniania, do którego należy poziom oceniania. |
| **Identyfikator jednostki oceny modelu**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmratingmodelentityid należący do mshr_hcmratingmodelentity | Wygenerowany przez system identyfikator modelu oceniania, do którego należy poziom oceniania. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opis poziomu oceny. |
| **Współczynnik**<br>mshr_factor<br>*Wartość całkowita* | Czytaj/zapisz<br>Potrzebne | Współczynnik poziomu oceny. Służy on do normalizacji wyników podczas porównywania towarów z różnymi numerami poziomów oceny. Wartość musi być liczbą całkowitą z liczby 0 do 9. |
| **Uwaga**<br>mshr_note<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Wszelkie notatki skojarzone z poziomem oceniania. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole, które ma być używane jako identyfikator rekordu encji. Kombinacja identyfikatora poziomu oceniania i identyfikatora modelu oceniania. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]