---
title: Adres pracownika listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3407128b0172f0e253d51bcfa23a894f981e21e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052296"
---
# <a name="payroll-worker-address"></a>Adres pracownika listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Adres pracownika listy płac w Dynamics 365 Human Resources.

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Miasto**<br>mshr_city<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Miasto zdefiniowane dla adresu.   |
| **Numer pracownika**<br>mshr_personnelnumber<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Unikalny numer personelu pracownika.  |
| **Kraj region**<br>mshr_countryregionid<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Region kraju zdefiniowany dla adresu  |
| **Data wejścia w życie**<br>mshr_postaladdressvalidfrom<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data, od której adres jest ważny. |
| **Pracował w adresie**<br>mshr_isworkedinaddressbr>*Int32* | Tylko do odczytu<br>Potrzebne | Wskazuje, czy adres jest miejscem pracy pracownika. |
| **Powiat**<br>mshr_county<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Hrabstwo zdefiniowane dla adresu.  |
| **Identyfikator adresu pracownika listy płac**<br>mshr_payrollworkeraddressentityid<br>*GUID* | Potrzebne<br>Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania adresu.  |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |  |
| **Ulica**<br>mshr_street<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Ulica określona dla adresu. |
| **Data ważności**<br>mshr_postaladdressvalidto<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data, do której adres jest ważny.  |
| **Identyfikator lokalizacji**<br>mshr_locationidbr>*Ciąg* | Tylko do odczytu <br>Potrzebne | Identyfikator dla adresu.  |
| **Kod pocztowy**<br>mshr_zipcode<br>*Ciąg* | Tylko do odczytu <br>Potrzebne |Numer identyfikacji zdefiniowany dla pracownika.  |
| **Mieszkał pod adresem**<br>mshr_islivedinaddressbr>*Ciąg* | Tylko do odczytu<br>Potrzebne | Wskazuje, czy adres jest miejscem zamieszkania pracownika. |
| **Stanowy**<br>mshr_state<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Stan określony dla adresu.  |

## <a name="example-query"></a>Przykład kwerendy

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Odpowiedź**

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
