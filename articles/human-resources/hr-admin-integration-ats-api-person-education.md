---
title: Wykształcenie osoby
description: W tym temacie opisano jednostkę Wykształcenia osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5e24188674c7746794c0e531dea21aa9b7f57b3534d4b67298cad19b6bec2a53
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731374"
---
# <a name="person-education"></a>Wykształcenie osoby

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano jednostkę Wykształcenia osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmpersoneducationentity

## <a name="description"></a>opis

Ta jednostka zawiera historię wykształcenia osoby, która jest kandydatem. Wykształcenie jest powiązane z rekordem osoby, co umożliwia powiązanie edukacji z innymi rolami utworzonymi dla tej osoby oprócz rekordu kandydata (pracownik, wykonawca itp.).

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki Wykształcenia osoby**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne | Wygenerowany przez system unikalny identyfikator dla rekordu jednostki wykształcenia osoby. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Unikatowy identyfikator rekordu strony (osoby) kandydata. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_dirpersonentity | Wygenerowany przez system unikalny identyfikator rekordu osoby kandydata. |
| **Podstawa zaliczenia**<br>mshr_creditbasis<br>*zestaw opcji mshr_hcmeducationcreditbasis* | Czytaj/zapisz<br>Opcjonalny | Podstawa zaliczenia stopnia wykształcenia. |
| **Ukończone zajęcia**<br>mshr_creditscompleted<br>*Dziesiętny* | Czytaj/zapisz<br>Opcjonalny | Liczba ukończonych zajęć stopnia wykształcenia. |
| **Uzyskane zaliczenia**<br>mshr_creditsearned<br>*Dziesiętny* | Czytaj/zapisz<br>Opcjonalny | Liczba zaliczeń zdobytych za stopień w toku dla rekordu wykształcenia. |
| **Potrzebne zaliczenia**<br>mshr_creditsneeded<br>*Dziesiętny* | Czytaj/zapisz<br>Opcjonalny | Liczba zaliczeń wymaganych do uzyskania stopnia w toku. |
| **Opis**<br>mshr_description<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis stopnia kandydata. |
| **Identyfikator poziomu wykształcenia**<br>mshr_educationlevelid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Identyfikator poziomu wykształcenia. | 
| **Wartość identyfikatora poziomu edukacji**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmeducationdegreeentityid jednostki mshr_hcmeducationdegreeentity | Wygenerowany przez system identyfikator rekordu stopnia wykształcenia. Ten identyfikator określa stopnie i poziomy wykształcenia zdefiniowane dla organizacji. |
| **Identyfikator dziedziny wykształcenia**<br>mshr_educationdisciplineid<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne<br>Klucz obcy: EducationDiscipline | Identyfikator dziedziny wykształcenia. |
| **Wartość identyfikatora dziedziny wykształcenia**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_hcmeducationdisciplineentityid jednostki mshr_hcmeducationdisciplineentity | Wygenerowany przez system unikalny identyfikator dyscypliny edukacji rekordu edukacji. |
| **Kierunek dodatkowy**<br>mshr_secondaryemphasis<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Dodatkowy kierunek zdobytego stopnia wykształcenia. |
| **Identyfikator instytucji edukacyjnych**<br>mshr_educationinstitutionid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Identyfikator uczęszczanej instytucji edukacyjnej. |
| **Wartość identyfikatora instytucji edukacyjnej**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmeducationinstitutionentityid jednostki mshr_hcmeducationinstitutionentity | Wygenerowany przez system identyfikator instytucji kształcenia. |
| **Data rozpoczęcia**<br>mshr_startdate<br>*Data/godzina* | Czytaj/zapisz<br>Opcjonalny | Data rozpoczęcia kształcenia dla uzyskanego stopnia. |
| **Data końcowa**<br>mshr_enddate<br>*Data/godzina* | Czytaj/zapisz<br>Potrzebne | Data wydania poświadczeń. |
| **Czas trwania**<br>mshr_duration<br>*Dziesiętny* | Czytaj/zapisz<br>Opcjonalny | Rekord czasu trwania wykształcenia. |
| **Jednostka czasu trwania**<br>mshr_durationunit<br>*zestaw opcji mshr_periodunit* | Czytaj/zapisz<br>Opcjonalny | Jednostka czasu związana z czasem trwania rekordu wykształcenia. |
| **Średnia ocen w punktach**<br>mshr_gradepointaverage<br>*Dziesiętny* | Czytaj/zapisz<br>Opcjonalny | Średnia uzyskanych ocen podczas procesu kształcenia. |
| **Skala ocen**<br>mshr_gradescale<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Skala ocen podczas procesu kształcenia. |
| **Notatki**<br>mshr_notes<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Notatki do wykorzystania przez rekrutację lub menedżera ds. zatrudniania. |
| **Pole główne**<br>mshr_primaryfield<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Pole używane jako inny podstawowy identyfikator rekordu jednostki. Połączenie numeru partii, identyfikatora dyscypliny edukacyjnej, identyfikatora instytucji edukacyjnej i identyfikatora poziomu edukacji. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]