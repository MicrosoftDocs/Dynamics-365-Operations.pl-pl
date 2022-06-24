---
title: Wynagrodzenie — częstotliwość wypłat
description: Ten artykuł zawiera szczegółowe informacje i przykładowe zapytanie dla encji Częstotliwość wynagrodzenia w Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9afe27776797b2355a32226bbd7fa514b5c5d962
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894622"
---
# <a name="compensation-pay-frequency"></a>Wynagrodzenie — częstotliwość wypłat


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ten artykuł zawiera szczegółowe informacje i przykładowe zapytanie dla encji Częstotliwość wynagrodzenia w Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpayrateconversionentity.

### <a name="description"></a>Opis

Ta jednostka zawiera informacje dotyczące konwersji stawki płacy dla danej częstotliwości wypłat wynagrodzenia.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | Opis |
| --- | --- | --- |
| **Konwersja rocznej stawki płacy**</br>mshr_annualconversionfactor</br>*Liczba dziesiętna* | Tylko do odczytu | Roczny współczynnik konwersji dla częstotliwości płatności. |
| **Opis**</br>mshr_description</br>*Ciąg* | Tylko do odczytu | Opis współczynnika konwersji. |
| **Konwersja godzinowej stawki płacy**</br>mshr_hourlyconversionfactor</br>*Liczba dziesiętna* | Tylko do odczytu | Godzinowy współczynnik konwersji dla częstotliwości płatności. |
| **Konwersja miesięcznej stawki płacy**</br>mshr_monthlyconversionfactor</br>*Liczba dziesiętna* | Tylko do odczytu | Miesięczny współczynnik konwersji dla częstotliwości płatności. |
| **Konwersja stawki płacy**</br>mshr_payrateconversion</br>*Ciąg* | Tylko do odczytu | Unikatowy ciąg identyfikujący współczynnik konwersji. |
| **Okres**</br>mshr_period</br>*Zestaw opcji okresu* | Tylko do odczytu | Okres główny danej konwersji stawki płacy. |
| **Konwersja tygodniowej stawki płacy**</br>mshr_weeklyconversionfactor</br>*Liczba dziesiętna* | Tylko do odczytu | Tygodniowy współczynnik konwersji dla częstotliwości płatności. |
| **Identyfikator obszaru danych**</br>mshr_dataareaid</br>*Ciąg* | Tylko do odczytu | Osoba prawna (firmę). |
| **Identyfikator podmiotu o częstotliwości wypłaty odszkodowania**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Wygenerowany przez system | Wygenerowana przez system wartość unikatowego globalnego identyfikatora (GUID) umożliwiająca jednoznaczną identyfikację rekordu. |

## <a name="example-query-for-payroll-employee"></a>Przykładowa kwerenda dla pracownika na liście płac

**Wniosek**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Odpowiedź**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
