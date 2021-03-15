---
title: Typy kontroli
description: W tym temacie opisano jednostkę Typy kontroli dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 227c15acb44e020ea9858961e45c11ad07e18a74
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126177"
---
# <a name="screening-types"></a>Typy kontroli

W tym temacie opisano jednostkę Typy kontroli dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmscreeningtypeentity

## <a name="description"></a>opis

Podmiot ten opisuje typy kontroli ustanowione przez firmę dla procesów poprzedzających zatrudnienie i trwających kontroli pracowników.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki typu kontroli**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Unikalny identyfikator podstawowy dla typu kontroli rekordu. |
| **Identyfikator typu kontroli**<br>mshr_screeningtypeid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Unikalny identyfikator zdefiniowany przez użytkownika dla typu kontroli. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opis typu kontroli. |
| **Jednostka częstotliwości**<br>mshr_frequencyunit<br>*zestaw opcji mshr_hcmfrequencyunit* | Czytaj/zapisz<br>Potrzebne | Opisuje częstotliwość, z jaką kontrola musi zostać zakończona dla przypisanej osoby. |
| **Generuj formularz**<br>mshr_generatefrom<br>*zestaw opcji mshr_hcmfrequencygeneratefrom* | Czytaj-zapisz<br>Potrzebne | Jeśli wartość Częstotliwość jest dowolną wartością inną niż „Tylko raz”, wartość GenerateFrom określa datę, od której ma zostać obliczone następne zdarzenie przesiewowe. |
| **Zakres częstotliwości**<br>mshr_frequencyinterval<br>*Wartość całkowita* | Czytaj-zapisz<br>Potrzebne | Jeśli wartość Częstotliwość ma wartość inną niż „Tylko raz”, należy zdefiniować interwał jednostek czasu między poszczególnymi zdarzeniami kontroli. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]