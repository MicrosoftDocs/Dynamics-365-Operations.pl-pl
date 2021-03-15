---
title: Doświadczenie zawodowe osoby
description: W tym temacie opisano jednostkę Doświadczenie zawodowe osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 51dd993e2d43174e96c062e142021cc0f6e3a288
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125288"
---
# <a name="person-professional-experience"></a>Doświadczenie zawodowe osoby

W tym temacie opisano jednostkę Doświadczenie zawodowe osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>opis

Ta jednostka zawiera opis doświadczenia zawodowego lub historii pracy kandydata.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki doświadczenia zawodowego osoby**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikatowy identyfikator rekordu jednostki. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Unikatowy identyfikator rekordu osoby kandydata. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system unikalny identyfikator dla rekordu jednostki osoby. |
| **Stanowisko pracodawcy**<br>mshr_employerposition<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Stanowisko posiadane przez kandydata w trakcie zatrudnienia. |
| **Nazwisko pracodawcy**<br>mshr_employername<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Nazwisko pracodawcy. |
| **Lokalizacja pracodawcy**<br>mshr_employerlocation<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Lokalizacja pracodawcy. Maksymalna długość: 60. Nie zdefiniowano określonego formatu ani nie jest wymagany. |
| **Telefon**<br>mshr_phone<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer telefonu pracodawcy. |
| **URL**<br>mshr_url<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Adres URL witryny sieci web pracodawcy. |
| **Data rozpoczęcia**<br>mshr_startdate<br>*Data/godzina* | Czytaj/zapisz<br>Potrzebne | Data rozpoczęcia zatrudnienia kandydata. |
| **Data końcowa**<br>mshr_enddate<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalny | Data zakończenia zatrudnienia kandydata lub nieważna, jeśli kandydat nadal jest tutaj zatrudniony. |
| **Zezwalaj na kontakt z pracodawcą**<br>mshr_allowcontactemployer<br>*zestaw opcji mshr_hrmblankyesno* | Czytaj/zapisz<br>Opcjonalny | Wskazuje, czy kandydat umożliwia kontakt z poprzednim pracodawcą. |
| **Notatki**<br>mshr_note<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Notatki do wykorzystania przez rekrutację lub menedżera ds. zatrudniania. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole używane jako podstawowy identyfikator rekordu jednostki. Kombinacja numeru strony, daty rozpoczęcia, stanowiska pracodawcy i imię pracodawcy. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]