---
title: Typ certyfikatu
description: W tym temacie opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798400"
---
# <a name="certificate-type"></a>Typ certyfikatu

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę typu certyfikatu dla Dynamics 365 Human Resources.

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