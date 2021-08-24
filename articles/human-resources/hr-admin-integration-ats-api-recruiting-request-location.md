---
title: Lokalizacja wniosku o rekrutację
description: W tym temacie opisano jednostkę Lokalizacja wniosku rekrutacji dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 59b625bded2116007b353e7a6b697c30a62550d5b25d05185ecffe1401fbff27
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759750"
---
# <a name="recruiting-request-location"></a>Lokalizacja wniosku o rekrutację

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Lokalizacja wniosku rekrutacji dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>opis

Lista lokalizacji zdefiniowanych jako lokalizacje, w których rekrutowani pracownicy będą pracować po zatrudnieniu. Są to lokalizacje utworzone w różnych firmach.

### <a name="json-representation"></a>Reprezentacja JSON

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator lokalizacji**<br>mshr_locationid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Wygenerowany przez system, czytelny dla użytkownika identyfikator miejsca rekrutacji. |
| **Lokalizacja wniosku o rekrutację**<br>mshr_recruitingrequestlocationid<br>*Ciąg* | Odpisz raz<br>Potrzebne | Zdefiniowany przez użytkownika unikalny identyfikator miejsca rekrutacji. |
| **Identyfikator jednostki lokalizacji wniosku o rekrutację**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikalny identyfikator rekordu lokalizacji we wniosku rekrutacji. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Opis lokalizacji. |
| **Identyfikator regionu/kraju**<br>mshr_countryregionid<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Określa kraj lub region, w którym kandydat posiada obywatelstwo. |
| **Wartość identyfikatora regionu kraju**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_logisticaddresscountryregionentityid jednostki mshr_logisticsaddresscountryregionentity | Wygenerowany przez system unikalny identyfikator kraju / regionu adresu. |
| **Kod Pocztowy**<br>mshr_zipcode<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Kod pocztowy. |
| **Ulica**<br>mshr_street<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Ulica w adresie. |
| **Miasto**<br>mshr_city<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Miasto. |
| **Stanowy**<br>mshr_state<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Województwo lub prowincja. |
| **Powiat**<br>mshr_county<br>*Ciąg* | Tylko do odczytu<br>Opcjonalny | Powiat. |
| **Telefon**<br>mshr_telephone<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer telefonu do lokalizacji. |
| **Wiadomość e-mail**<br>mshr_email<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Adres e-mail. |
| **AdresInternetowy**<br>mshr_internetaddress<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Adres URL witryny sieci Web lokalizacji. |
| **Identyfikator obszaru danych**<br>mshr_dataareaid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Określa osobę prawną (firmę). |
| **Wartość identyfikatora obszaru danych**<br>_mshr_dataareaid_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: cdm_companyid jednostki cdm_company obcej | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę). |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]