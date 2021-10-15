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
ms.openlocfilehash: bf3fc5f333333b9a832ecb9c185473e476ac231d
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559516"
---
# <a name="payroll-worker-address"></a>Adres pracownika listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę adresu pracownika listy płac dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_payrollworkeraddressentity.

### <a name="description"></a>opis

Ta jednostka podaje miejsce zamieszkania i miejsca pracy płacowej dla danego pracownika.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | Opis |
| --- | --- | --- |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu | Unikalny numer personelu pracownika. |
| **Identyfikator lokalizacji**</br>mshr_locationidbr>*Ciąg* | Tylko do odczytu | Identyfikator dla adresu. |
| **Mieszkał pod adresem**</br>mshr_islivedinaddressbr </br> *[zestaw opcji mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Tylko do odczytu | Wartość wskazująca, czy adres jest adresem miejsca zamieszkania pracownika. |
| **Pracował w adresie** </br> mshr_isworkedinaddressbr </br>*[zestaw opcji mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Tylko do odczytu | Wartość wskazująca, czy adres jest adresem miejsca pracy pracownika. |
| **Kraj region**</br>mshr_countryregionid</br>*Ciąg* | Tylko do odczytu</br>Potrzebne | Kraj lub region zdefiniowany dla adresu. |
| **Kod pocztowy**</br>mshr_zipcode<br>*Ciąg* | Tylko do odczytu | Numer identyfikacyjny zdefiniowany dla pracownika. |
| **Ulica**</br>mshr_street</br>*Ciąg* | Tylko do odczytu | Ulica określona dla adresu. |
| **Miasto**</br>mshr_city</br>*Ciąg* | Tylko do odczytu | Miasto zdefiniowane dla adresu. |
| **Stanowy**</br>mshr_state</br>*Ciąg* | Tylko do odczytu | Stan lub prowincja zdefiniowana dla adresu. |
| **Powiat**</br>mshr_county</br>*Ciąg* | Tylko do odczytu | Powiat zdefiniowany dla adresu. |
| **Data wejścia w życie**</br>mshr_postaladdressvalidfrom</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data, od której adres jest ważny. |
| **Data ważności**</br>mshr_postaladdressvalidto</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data, do której adres jest ważny. |
| **Pole główne**</br>mshr_primaryfield</br>*Ciąg* | Tylko do odczytu | Pole główne. |
| **Identyfikator adresu pracownika listy płac**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość unikatowego globalnego identyfikatora (GUID) umożliwiająca jednoznaczną identyfikację adresu. |

## <a name="relations"></a>Relacje

| Wartości właściwości | Encja powiązana | Właściwość nawigacji | Typ kolekcji |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

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

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
