---
title: Osoba
description: W tym temacie opisano jednostkę Osoby dla Dynamics 365 Human Resources.
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
ms.openlocfilehash: e61b768c5194b52178853d48c50dbf072eebbdcd
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125456"
---
# <a name="person"></a>Osoba

W tym temacie opisano jednostkę Osoby dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_dirpersonentity

### <a name="description"></a>opis

Ta jednostka udostępnia dane osobowe osoby, która jest kandydatem.

## <a name="json-representation"></a>Reprezentacja JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Właściwości

| Właściwość<br>**Nazwa fizyczna**<br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Identyfikator jednostki osoby**<br>mshr_dirpersonentityid<br>*GUID* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Wygenerowany przez system unikatowy identyfikator rekordu jednostki. |
| **Numer strony**<br>mshr_partynumber<br>*Ciąg* | Tylko do odczytu<br>Potrzebne<br>Wygenerowany przez system | Czytelny dla użytkownika, wygenerowany przez system, niepowtarzalny identyfikator osoby.  |
| **Imię i nazwisko**<br>mshr_name<br>*Ciąg* | Tylko do odczytu<br>Potrzebne | Wartość pola jest połączeniem imienia, drugiego imienia, prefiksu nazwiska i nazwiska w kolejności zdefiniowanej w polu **Sekwencja nazw Wyświetl jako**. |
| **Alias nazwy**<br>mshr_namealias<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Alias, który może być podany dla osoby. |
| **Alternatywna nazwa**<br>mshr_knownas<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Imię, które może być używane dla osoby, jeśli jest zwykle znane jako inne imię. |
| **Identyfikator języka**<br>mshr_languageid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Identyfikator języka podstawowego języka danej osoby, zgodnie z formatem ISO 639-1. |
| **Książki adresowe**<br>mshr_addressbooks<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Książka adresowa, do której można przypisać osobę. Książki adresowe, które zostały skonfigurowane dla organizacji, są wymienione w jednostce mshr_diraddressbooksentity. |
| **Dzień rocznicy**<br>mshr_anniversaryday<br>*Int* | Czytaj/zapisz<br>Opcjonalny | Dzień rocznicy osoby. |
| **Miesiąc rocznicy**<br>mshr_anniversarymonth<br>*zestaw opcji mshr_monthsofyear* | Czytaj/zapisz<br>Opcjonalny | Miesiąc rocznicy osoby. |
| **Rok rocznicy**<br>mshr_anniversaryyear<br>*Int* | Czytaj/zapisz<br>Opcjonalny | Rok rocznicy osoby. |
| **Dzień urodzenia**<br>mshr_birthday<br>*Int* | Czytaj/zapisz<br>Opcjonalny | Dzień urodzin osoby. |
| **Miesiąc urodzenia**<br>mshr_birthmonth<br>*zestaw opcji mshr_monthsofyear* | Czytaj/zapisz<br>Opcjonalny | Miesiąc urodzin osoby. |
| **Rok urodzenia**<br>mshr_birthyear<br>*Int* | Czytaj/zapisz<br>Opcjonalny | Rok urodzin osoby. |
| **Imiona dzieci**<br>mshr_childrennames<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Ciąg imion dzieci osoby. Nie ma wymaganego rozgraniczania. |
| **Rodzaj**<br>mshr_gender<br>*zestaw opcji mshr_hcmpersongender* | Czytaj/zapisz<br>Opcjonalny | Płeć kulturowa osoby. |
| **Hobby**<br>mshr_hobbies<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Hobby danej osoby. |
| **Inicjały**<br>mshr_initials<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Inicjały nazwiska osoby. |
| **Stan cywilny**<br>mshr_maritalstatus<br>*zestaw opcji mshr_hcmpersonmaritalstatus* | Czytaj/zapisz<br>Opcjonalny | Stan cywilny osoby. |
| **Imię fonetycznie**<br>mshr_phoneticfirstname<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Fonetyczna wymowa imienia osoby. |
| **Nazwisko fonetycznie**<br>mshr_phoneticlastname<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Fonetyczna wymowa nazwiska osoby. |
| **Drugie imię fonetyczne**<br>mshr_phoneticmiddlename<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Fonetyczna wymowa nazwiska osoby. |
| **Osobisty sufiks**<br>mshr_personalsuffix<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Osobisty sufiks osoby. Prawidłowe wartości w jednostce mshr_dirnameaffixentity, gdzie mshr_type to sufiks (200000001). |
| **Tytuł osobisty**<br>mshr_personaltitle<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Osobisty tytuł osoby. Prawidłowe wartości w jednostce mshr_dirnameaffixentity, gdzie mshr_type to Tytuł (200000000).
| **Sufiks zawodowy**<br>mshr_professionalsuffix<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Sufiks zawodowy. |
| **Tytuł zawodowy**<br>mshr_professionaltitle<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Tytuł zawodowy. |
| **Pełny adres podstawowy:**<br>mshr_fullprimaryaddress<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Pełny adres podstawowy osoby, będący połączeniem głównych pól adresu. |
| **Adres - miasto**<br>mshr_addresscity<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Miasto w podstawowym adresie osoby. Ustaw w jednostce mshr_logisticsaddresscityentity. |
| **Adres Kraj Region**<br>mshr_addresscountryregionid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kraj/region podstawowego adresu osoby. Prawidłowe wartości w jednostce mshr_logisticsaddresscountryregionentity. |
| **Adres Kod ISO kraju regionu**<br>mshr_addresscountryregionisocode<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kod ISO kraju podstawowego adresu osoby. |
| **Adres Hrabstwo**<br>mshr_addresscounty<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kraj w podstawowym adresie osoby. Ustaw w jednostce mshr_logisticsaddresscountyentity. |
| **Adres Nazwa okręgu**<br>mshr_addressdistrictname<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Okręg głównego adresu osoby. Ustaw w jednostce mshr_logisticsaddressdistrictentity. |
| **Szerokość geograficzna adresu**<br>mshr_addresslatitude<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Szerokość geograficzna głównego adresu osoby. |
| **Identyfikator adresu lokalizacji**<br>mshr_addresslocationid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Unikatowy identyfikator lokalizacji podstawowego adresu osoby. Prawidłowe wartości w jednostce mshr_logisticspostaladdresslocationcdsentity. |
| **Role adresu lokalizacji**<br>mshr_addresslocationroles<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Rola lokalizacji podstawowego adresu osoby. Ustaw w jednostce mshr_logisticslocationrolecdsentity. |
| **Długość geograficzna adresu**<br>mshr_addresslongitude<br>*Ciąg* |  Czytaj/zapisz<br>Opcjonalny | Długość geograficzna głównego adresu osoby. |
| **Stan w adresie**<br>mshr_addressstate<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Stan w podstawowym adresie osoby. Ustaw w jednostce mshr_logisticsaddressstateentity. |
| **Ulica w adresie**<br>mshr_addressstreet<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Ulica podstawowego adresu osoby. |
| **Adres ważny od**<br>mshr_addressvalidfrom<br>*Data* | Czytaj/zapisz<br>Opcjonalny | Data, od której obowiązuje podstawowy adres osoby. |
| **Adres ważny do**<br>mshr_addressvalidto<br>*Data* | Czytaj/zapisz<br>Opcjonalny | Data, do której obowiązuje podstawowy adres osoby. |
| **Kod pocztowy w adresie**<br>mshr_addresszipcode<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Kod pocztowy głównego adresu osoby. Ustaw w jednostce mshr_logisticsaddresspostalcodeentity. |
| **Adres jest prywatny**<br>mshr_addressisprivate<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Określa, czy główny adres osoby jest udostępniany innym osobom w organizacji. |
| **Opis adresu**<br>mshr_addressdescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis głównego adresu osoby. |
| **Podstawowy adres e-mail osoby kontaktowej**<br>mshr_primarycontactemail<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Podstawowy adres e-mail osoby. |
| **Opis głównego adresu e-mail osoby kontaktowej**<br>mshr_primarycontactemaildescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla podstawowego adresu e-mail. |
| **Podstawowym adresem e-mail osoby kontaktowej jest komunikator**<br>mshr_primarycontactemailisim<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Określa, czy podstawowy adres e-mail jest dostępny w wiadomościach błyskawicznych. |
| **Cel podstawowego głównego adresu e-mail osoby kontaktowej**<br>mshr_primarycontactemailpurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego adresu e-mail. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Podstawowy faks osoby kontaktowej**<br>mshr_primarycontactfax<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Główny numer faksu. |
| **Opis głównego faksu osoby kontaktowej**<br>mshr_primarycontactfaxdescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla podstawowego faksu. |
| **Numer wewnętrzny podstawowego faksu osoby kontaktowej**<br>mshr_primarycontactfaxextension<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer wewnętrzny podstawowego numeru faksu. |
| **Cel podstawowego głównego faksu osoby kontaktowej**<br>mshr_primarycontactfaxpurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego numeru faksu. Ustaw w jednostce mshr_logisticslocationroleentity.
| **Podstawowy numer telefonu osoby kontaktowej**<br>mshr_primarycontactphone<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Główny numer telefonu. |
| **Opis głównego numeru telefonu osoby kontaktowej**<br>mshr_primarycontactphonedescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla podstawowego numeru telefonu. |
| **Numer wewnętrzny podstawowego numeru telefonu osoby kontaktowej**<br>mshr_primarycontactphoneextension<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Numer wewnętrzny podstawowego numeru telefonu. |
| **Podstawowym numerem telefonu kontaktowego jest telefon komórkowy**<br>mshr_primarycontactphoneismobile<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Określa, czy podstawowy numer telefonu to telefon komórkowy. |
| **Cel podstawowego numeru telefonu osoby kontaktowej**<br>mshr_primarycontactphonepurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego numeru telefonu. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Podstawowy teleks osoby kontaktowej**<br>mshr_primarycontacttelex<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Główny numer teleksu. |
| **Opis głównego teleksu osoby kontaktowej**<br>mshr_primarycontacttelexdescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla podstawowego numeru teleksu osoby. |
| **Cel podstawowego numeru teleksu osoby kontaktowej**<br>mshr_primarycontacttelexpurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel dla podstawowego numeru teleksu osoby. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Podstawowy adres URL osoby kontaktowej**<br>mshr_primarycontacturl<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Podstawowy adres URL. |
| **Opis głównego adresu URL osoby kontaktowej**<br>mshr_primarycontacturldescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla głównego adresu URL osoby. |
| **Cel podstawowego głównego adresu URL osoby kontaktowej**<br>mshr_primarycontacturldescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego adresu URL osoby. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Facebook osoby kontaktowej**<br>mshr_primarycontactfacebook<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Podstawowe konto Facebook. Zidentyfikowane na podstawie nazwy użytkownika. |
| **Opis konta Facebook osoby kontaktowej**<br>mshr_primarycontactfacebookdescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla głównego konta Facebook osoby. |
| **Podstawowe konto Facebook osoby kontaktowej jest prywatne**<br>mshr_primarycontactfacebookisprivate<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Określa, czy główne konto Facebook jest widoczne dla innych użytkowników. |
| **Cel podstawowego głównego konta Facebook osoby kontaktowej**<br>mshr_primarycontactfacebookpurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego konta Facebook osoby. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Konto LinkedIn podstawowej osoby kontaktowej**<br>mshr_primarycontactlinkedin<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Główne konto LinkedIn. Zidentyfikowane na podstawie nazwy użytkownika. |
| **Opis konta LinkedIn głównej osoby kontaktowej**<br>mshr_primarycontactlinkedindescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla głównego konta LinkedIn osoby. |
| **Podstawowe konto LinkedIn osoby kontaktowej jest prywatne**<br>mshr_primarycontactlinkedinisprivate<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Określa, czy informacje o głównym koncie LinkedIn danej osoby są udostępniane innym użytkownikom. |
| **Cel konta LinkedIn podstawowej osoby kontaktowej**<br>mshr_primarycontactlinkedinpurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego konta LinkedIn osoby. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Konto Twitter głównej osoby kontaktowej**<br>mshr_primarycontacttwitter<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Główne konto w serwisie Twitter danej osoby. Zidentyfikowane na podstawie @nazwa użytkownika. |
| **Opis podstawowego konta Twitter osoby kontaktowej**<br>mshr_primarycontacttwitterdescription<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Opis podany dla głównego konta Twitter osoby. |
| **Podstawowe konto Twitter osoby kontaktowej jest prywatne**<br>mshr_primarycontacttwitterisprivate<br>*zestaw opcji mshr_noyes* | Czytaj/zapisz<br>Opcjonalny | Określa, czy informacje o głównym koncie Twitter danej osoby są udostępniane innym użytkownikom. |
| **Cel konta Twitter podstawowej osoby kontaktowej**<br>mshr_primarycontacttwitterpurpose<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Cel podstawowego konta Twitter osoby. Ustaw w jednostce mshr_logisticslocationroleentity. |
| **Typ strony**<br>mshr_partytype<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Typ strony osoby. Będzie zawsze **Osobą** dla kandydatów. |
| **Wyświetlanie sekwencji nazw jako**<br>mshr_namesequencedisplayas<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Sekwencja, w której właściwości nazwiska osoby są łączone w celu utworzenia wartości właściwości Nazwa (mshr_name). |
| **Imię**<br>mshr_firstname<br>*Ciąg* | Czytaj/zapisz<br>Potrzebne | Imię osoby. |
| **Drugie imię**<br>mshr_middlename<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Drugie imię osoby. |
| **Prefiks nazwiska**<br>mshr_lastnameprefix<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Prefiks nazwiska osoby. |
| **Nazwisko**<br>mshr_lastname<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Nazwisko osoby. |
| **Identyfikator lokalizacji elektronicznej**<br>mshr_electroniclocationid<br>*Ciąg* | Czytaj/zapisz<br>Opcjonalny | Identyfikator elektronicznej lokalizacji osoby. |
| **Adres Strefa czasowa**<br>mshr_addresstimezone<br>*Int* | Czytaj/zapisz<br>Opcjonalny | Strefa czasowa podstawowego adresu osoby. |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>
[Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]