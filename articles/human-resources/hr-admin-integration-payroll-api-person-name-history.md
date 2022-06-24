---
title: Historia nazwiska osoby
description: Ten artykuł zawiera szczegóły i przykładowe zapytanie dla jednostki Historia nazw osób w Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e34b0d7bebd1c4037347161087ff3a4485a58878
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875779"
---
# <a name="person-name-history"></a>Historia nazwiska osoby


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Historia nazw osób w Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Opis

Podmiot ten dostarcza informacji o historii nazwisk dla danej osoby.

> [!IMPORTANT] 
> Pola **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** i **NameValidTo** nie będą już dostępne w tej encji Pracownik listy płac. Zostały one usunięte, aby zapewnić, że tylko jedno źródło danych z datą obowiązującą obsługuje tę jednostkę.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | Opis |
| --- | --- | --- |
| **Imię**</br>mshr_firstname</br>*Ciąg* | Tylko do odczytu | Imię. |
| **Prefiks nazwiska**</br>mshr_lastnameprefix</br>*Ciąg*) | Tylko do odczytu | Prefiks nazwiska. |
| **Nazwisko**</br>mshr_lastname</br>*Ciąg*) | Tylko do odczytu | Nazwisko. |
| **Drugie imię**</br>mshr_middlename</br>*Ciąg*) | Tylko do odczytu | Drugie imię. |
| **Data ważności**</br>mshr_validto</br>*Ciąg*) | Tylko do odczytu | Data, do której imię jest ważne. |
| **Numer strony**</br>mshr_partynumber</br>*Ciąg* | Tylko do odczytu | Czytelny dla użytkownika, wygenerowany przez system, niepowtarzalny identyfikator osoby. |
| **Pole główne**</br>mshr_primaryfield</br>*Ciąg* | Tylko do odczytu | Unikalny identyfikator rekordu. |
| **Identyfikator jednostki historii imienia i nazwiska osoby**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość unikatowego globalnego identyfikatora (GUID) umożliwiająca jednoznaczną identyfikację rekordu. |

## <a name="relations"></a>Relacje

| Wartości właściwości | Encja powiązana | Właściwość nawigacji | Typ kolekcji |
| --- | --- | --- | --- |
| Nie dotyczy | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | Nie dotyczy | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Przykładowa kwerenda dla pracownika na liście płac

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Odpowiedź**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
