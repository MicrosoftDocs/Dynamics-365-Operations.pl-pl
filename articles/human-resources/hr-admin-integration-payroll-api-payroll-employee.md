---
title: Pracownik etatowy listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące jednostki Pracownik etatowy na liście płac w Dynamics 365 Human Resources.
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
ms.openlocfilehash: 57501d07f6b9cffdff9f37737df8c278c574cf30
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314292"
---
# <a name="payroll-employee"></a>Pracownik etatowy listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano encję Pracownik listy płac dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_payrollemployeeentity.

### <a name="description"></a>opis

Ta jednostka zawiera informacje o pracowniku. Musisz ustawić [parametry integracji listy płac](hr-admin-integration-payroll-api-parameters.md) przed użyciem tej jednostki.

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Numer pracownika**<br>mshr_personnelnumber<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Unikalny numer personelu pracownika. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Potrzebne<br>Wygenerowany przez system |  |
| **Nazwisko**<br>mshr_lastname<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Nazwisko pracownika. |
| **Identyfikator firmy**<br>mshr_legalentityID<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Określa osobę prawną (firmę). |
| **Data wejścia w życie**<br>mshr_namevalidfrom<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data, od której ważne są informacje o pracowniku.  |
| **Rodzaj**<br>mshr_gender<br>[zestaw opcji mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Tylko do odczytu<br>Potrzebne | Płeć pracownika. |
| **Identyfikator jednostki Pracownik listy płac**<br>mshr_payrollemployeeentityid<br>*GUID* | Potrzebne<br>Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID w celu unikatowego zidentyfikowania pracownika. |
| **Data rozpoczęcia zatrudnienia**<br>mshr_employmentstartdate<br>*Przesunięcie daty i godziny* | Tylko do odczytu<br>Potrzebne | Data rozpoczęcia zatrudnienia pracownika. |
| **Identyfikator typu identyfikacji**<br>mshr_identificationtypeid<br>*Ciąg* |Tylko do odczytu<br>Potrzebne | Typ identyfikacji zdefiniowany dla pracownika. |
| **Data zakończenia zatrudnienia**<br>mshr_employmentenddate<br>*Przesunięcie daty i godziny* | Tylko do odczytu<br>Potrzebne |Data zakończenia zatrudnienia pracownika.  |
| **Identyfikator obszaru danych**<br>mshr_dataareaid_id<br>*GUID* | Potrzebne <br>Wygenerowany przez system | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę). |
| **Data ważności**<br>mshr_namevalidto<br>*Przesunięcie daty i godziny* |  Tylko do odczytu<br>Potrzebne | Data, do której ważne są informacje o pracowniku. |
| **Data urodzenia**<br>mshr_birthdate<br>*Przesunięcie daty i godziny* | Tylko do odczytu <br>Potrzebne | Data urodzenia pracownika |
| **Numer identyfikacyjn do**<br>mshr_identificationnumber<br>*Ciąg* | Tylko do odczytu <br>Potrzebne |Numer identyfikacji zdefiniowany dla pracownika.  |
| **Imię**<br>mshr_firstname<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Imię pracownika. |
| **Drugie imię**<br>mshr_middlename<br>*Ciąg* | Tylko do odczytu<br>Potrzebne |Drugie imię pracownika.  |

## <a name="example-query-for-payroll-employee"></a>Przykładowa kwerenda dla pracownika na liście płac

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
```

**Odpowiedź**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_firstname": "Cassie",
    "mshr_middlename": "Lassie",
    "mshr_lastname": "Hicks",
    "mshr_namevalidfrom": "2021-03-12T20:34:25Z",
    "mshr_namevalidto": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
    "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_dataareaid_id_value": null
}
```
## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]