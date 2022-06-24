---
title: Typ certyfikatu
description: W tym artykule opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: bfe7f06176098a504f8d2ad1c1431a6f60fe059c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886197"
---
# <a name="certificate-type"></a>Typ certyfikatu


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmcertificatetypeentity

## <a name="description"></a>opis

Ten podmiot definiuje listę typów certyfikatów zawodowych ustawionych w Human Resources. Ta jednostka nie jest specyficzna dla osoby prawnej (firmy).

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki typu certyfikatu**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne 
Wygenerowany przez system | Unikalny identyfikator podstawowy dla typu certyfikatu. |
| **Typ certyfikatu**<br>mshr_certificatetype<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Unikalny czytelny dla użytkownika identyfikator typu certyfikatu. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opis typu certyfikatu. |
| **Wymagaj odnowienia**<br>mshr_requirerenewal<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Wskazuje, czy dla certyfikatu jest wymagane odnowienie. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
