---
title: Kandydat do zatrudnienia
description: W tym artykule opisano jednostkę Kandydat do zatrudnienia dla Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/05/2021
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
ms.openlocfilehash: 7c243bdf81beabe9e1ee429227a6edf4d4864bfb
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832006"
---
# <a name="candidate-to-hire"></a>Kandydat do zatrudnienia


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule opisano jednostkę Kandydat do zatrudnienia dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_hcmcandidatetohireentity

## <a name="description"></a>opis

Ta jednostka udostępnia szczegóły kandydata używane do tworzenia pracownika w Dynamics 365 Human Resources. Służy do odczytywania wszystkich rekordów kandydatów oraz tworzenia wewnętrznych i zewnętrznych rekordów kandydatów, umożliwiając tworzenie danych osobowych nowego kandydata.

Tworząc zewnętrzny rekord kandydata, który będzie nowym rekordem osoby w systemie, nie możesz definiować numeru strony (osoby), zamieszczasz nowy rekord kandydata. Nowy rekord encji osoby jest tworzony z nowym rekordem kandydata.

Podczas tworzenia wewnętrznego rekordu kandydata (kandydata na stanowisko, który ma już rekord pracownika w firmie), dla właściwości mshr_partynumber w rekordzie kandydata należy zdefiniować numer partii (osoby), który już istnieje dla osoby, zamiast definiować dane osobowe (takie jak imię i nazwisko, płeć lub data urodzenia), które zostaną użyte do utworzenia nowego rekordu osoby.

## <a name="json-representation"></a>Reprezentacja JSON

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
            "mshr_militaryserviceenddate": "Date",
            "mshr_militaryservicestartdate": "Date"
        }
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki Kandydat do zatrudnienia**<br>mshr_hcmcandidatetohireentityid<br>Identyfikator Guid | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Wygenerowany przez system unikatowy identyfikator rekordu jednostki. |
| **Identyfikator kandydata**<br>mshr_candidateid<br>Ciąg | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Unikatowy identyfikator jednostki. |
| **Numer strony**<br>mshr_partynumber<br>Ciąg | Tylko do odczytu<br>Potrzebne | Numer strony (osoby) w aktach osobowych kandydata. |
| **Wartość identyfikatora osoby**<br>_mshr_fk_person_id_value<br>Identyfikator Guid | Tylko do odczytu<br>Potrzebne<br>Klucz obcy: mshr_dirpersonentityid jednostki mshr_direpersonentity | Wygenerowany przez system unikatowy identyfikator rekordu strony (osoby) kandydata. |
| **Typ strony**<br>mshr_partytype<br>zestaw opcji mshr_dirpartytype | Tylko do odczytu<br>Potrzebne | Typ strony rekordu określony w zestawie opcji mshr_dirpartytype. Dla tej jednostki typem zawsze będzie „Osoba”. |
| **Identyfikator wniosku o rekrutację**<br>mshr_recruitingrequestid<br>Ciąg | Odpisz raz<br>Opcjonalny | Odwołuje się do wniosku o rekrutację, które spełnia ten kandydat. |
| **Wartość identyfikatora wniosku o rekrutację**<br>_mshr_fk_recruitingrequest_id_value<br>Identyfikator Guid | Czytaj/zapisz<br>Opcjonalny<br>Klucz obcy: mshr_hcmrecruitingrequestentityid należący do jednostki mshr_hcmrecruitingrequestentity | Wygenerowany przez system unikalny identyfikator wniosku rekrutacyjnego, który spełnia kandydat. |
| **Identyfikator stanowiska**<br>mshr_positionid<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Identyfikator stanowiska, w którym jest traktowany kandydat. |
| **Wartość identyfikatora stanowiska**<br>_mshr_fk_position_if_value<br>Identyfikator Guid | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmpositionv2entityid jednostki mshr_hcmpositionv2entity | Pod uwagę brany jest wygenerowany przez system identyfikator stanowiska na kandydata. |
| **Imię**<br>mshr_firstname<br>Ciąg | Czytaj/zapisz<br>Potrzebne | Imię kandydata. |
| **Drugie imię**<br>mshr_middlename<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Drugie imię kandydata. |
| **Prefiks nazwiska**<br>mshr_lastnameprefix<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Prefiks nazwiska kandydata. |
| **Nazwisko**<br>mshr_lastname<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Nazwisko kandydata. |
| **Rodzaj**<br>mshr_gender<br>zestaw opcji mshr_hcmpersongender | Czytaj/zapisz<br>Opcjonalny | Płeć kandydata. |
| **Data urodzenia**<br>mshr_birthdate<br>Data/godzina | Czytaj/zapisz<br>Opcjonalny | Data urodzenia kandydata. |
| **Kod kraju obywatelstwa**<br>mshr_citizenshipcountrycode<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Określa kraj, w którym kandydat posiada obywatelstwo. Prawidłowe kody krajów są w mshr_logisticaddresscountryregionentity. |
| **Identyfikator stanu kombatanta**<br>mshr_veteranstatusid<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Wskazuje status weterana kandydata. |
| **Wartość identyfikatora statusu weterana**<br>_mshr_fk_veteranstatus_id_value<br>Identyfikator Guid | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmveteranstatusentityid jednostki mshr_hcmveteranstatusentity | Wygenerowany przez system unikalny identyfikator dla rekordu jednostki statusu weterana. |
| **Data rozpoczęcia służby wojskowej**<br>mshr_militaryservicestartdate<br>Data/godzina | Czytaj/zapisz<br>Opcjonalny | Data rozpoczęcia służby wojskowej kandydata. |
| **Data zakończenia służby wojskowej**<br>mshr_militaryserviceenddate<br>Data/godzina | Czytaj/zapisz<br>Opcjonalny | Data zakończenia służby wojskowej kandydata. |
| **Jest niepełnosprawnym kombatantem**<br>mshr_isdisabledveteran<br>zestaw opcji mshr_noyes | Czytaj/zapisz<br>Opcjonalny | Wskazuje, czy kandydat ma niepełnosprawny status weterana. |
| **Data dostępności**<br>mshr_availabilitydate<br>Data/godzina | Czytaj/zapisz<br>Opcjonalny | Najwcześniejszy termin, w którym kandydat będzie dostępny do pracy. |
| **Zgodzi się na przeprowadzkę**<br>mshr_iswillingtorelocate<br>zestaw opcji mshr_noyes | Czytaj/zapisz<br>Opcjonalny | Wskazuje, czy kandydat jest skłonny przenieść się na to stanowisko. |
| **Komentarze**<br>mshr_comments<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Komentarze do wykorzystania przez osobę rekrutującą lub osobę zatrudniającą. |
| **Wynik integracji aplikacji**<br>mshr_applcantintegrationresult<br>zestaw opcji mshr_applicantintegrationresult | Czytaj/zapisz<br>Potrzebne | Stan kandydata w procesie zatrudniania powiązanym z integracją. |
| **Identyfikator kodu przyczyny nie zatrudniania**<br>mshr_donothirereasoncodeid<br>Ciąg | Czytaj/zapisz<br>Opcjonalny | Opcjonalnie podawany kod przyczyny, gdy status (wynik integracji aplikacji) jest ustawiony na „Nie zatrudniony”. |
| **Wartość identyfikatora kodu przyczyny**<br>_mshr_fk_reasoncode_id_value<br>Identyfikator Guid | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: mshr_hcmreasoncodeentityid jednostki mshr_hcmreasoncodeentity | Wygenerowany przez system unikatowy identyfikator kodu przyczyny **Nie zatrudniaj**. |
| **Identyfikator obszaru danych**<br>mshr_dataareaid<br>Ciąg | Czytaj/zapisz<br>Opcjonalny |  Określa osobę prawną (firmę). |
| **Wartość identyfikatora obszaru danych**<br>_mshr_dataareaid_id_value<br>Identyfikator Guid | Tylko do odczytu<br>Opcjonalny<br>Klucz obcy: cdm_companyid jednostki cdm_company obcej | Wygenerowana przez system wartość identyfikatora GUID identyfikująca osobę prawną (firmę). |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
