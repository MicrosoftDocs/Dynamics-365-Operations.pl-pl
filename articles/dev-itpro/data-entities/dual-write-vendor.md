---
title: Zintegrowane dane główne dostawcy
description: W tym temacie opisano integrację danych dostawcy między programami Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 45808bc35aba04df6fcaf6b1cbfcc2461b0b65cb
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789230"
---
## <a name="integrated-vendor-master"></a>Zintegrowane dane główne dostawcy

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Termin *dostawca* odnosi się do organizacji dostawcy lub wyłącznego właściciela, będących częścią łańcucha dostaw i dostarczających towary dla firmy. Mimo że *dostawca* jest ustaloną koncepcją Microsoft Dynamics 365 for Finance and Operations, koncepcja dostawcy nie istnieje w Dynamics 365 for Customer Engagement. Zamiast tego niektóre firmy przeciążają encję Konto do przechowywania informacji o kliencie i informacje o dostawcy. Inne firmy stosują koncepcję dostawcy niestandardowego. Integracja Common Data Service wspiera oba te schematy. W związku z tym można włączyć jeden z nich, w zależności od scenariusza biznesowego.

Integracja danych dostawcy między programami Finance and Operations i Customer Engagement umożliwia wielowątkowe tworzenie danych głównych. Niezależnie od tego, skąd pochodzą dane dostawcy, jest on integrowany w tle w graniach wszystkich aplikacji i niezależnie od różnic w infrastrukturze. 

### <a name="vendor-data-flow"></a>Przepływ danych dostawcy

Jeśli chcesz użyć Customer Engagement do tworzenia danych głównych dostawcy i chcesz wyodrębnić informacje o dostawcy z informacji o kliencie, możesz skorzystać z nowego schematu dostawcy.

![Przepływ danych dostawcy](media/dual-write-vendor-data-flow.png)

Jeśli chcesz użyć Customer Engagement do tworzenia danych głównych dostawcy i chcesz dalej korzystać z encji Konto do przechowywania informacji o dostawcy, możesz skorzystać z nowego rozszerzonego schematu dostawcy. W tym projekcie rozszerzone informacje o dostawcy, takie jak grupa dostawców i profil księgowania dostawcy, są przechowywane w szczegółach dostawcy.

![Rozszerzony przepływ danych dostawcy](media/dual-write-vendor-detail.jpg)

Informacje kontaktowe dostawcy przypominają informacje kontaktowe klienta. W tle informacje osoby kontaktowej są przechowywane i pobierane z tych samych podmiotów.

## <a name="templates"></a>Szablony

Dane dostawcy obejmują wszystkie informacje o dostawcy, takie jak grupa dostawców, adresy, dane kontaktowe, profil płatności oraz profil faktury. Kolekcja mapy encji działa razem podczas interakcji z danymi dostawcy, jak pokazano w poniższej tabeli.

Finance and Operations  | Aplikacja Customer Engagement
------------------------|---------------------------------
Dostawca V2               | Konto
Dostawca V2               | Msdyn\_vendors
CDS Contacts wer. 2         | Osoba kontaktowa
Grupy dostawców           | Msdyn\_vendorgroups
Metoda płatności dostawcy   | Msdyn\_vendorpaymentmethods
Harmonogram płatności        | Msdyn\_paymentschedules
Harmonogram płatności        | Msdyn\_paymentschedulelines
Dzień zapłaty w usłudze CDS         | Msdyn\_paymentdays
Wiersze dni zapłaty w usłudze CDS   | Msdyn\_paymentdaylines
Warunki płatności        | Msdyn\_paymentterms
Afiksy nazwy            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Dostawca V2 i Konto 

Firmy, które używają encji Konto do przechowywania informacji o dostawcy, mogą nadal używać go w taki sam sposób. Mogą również korzystać z funkcji jawnego dostawcy dostępnej w wyniku integracji z programem Finance and Operations.

## <a name="vendor-v2-and-msdyn_vendors"></a>Dostawca V2 i Msdyn\_vendors

Firmy, które korzystają z niestandardowego rozwiązania dla dostawców, mogą skorzystać z koncepcji dostawcy gotowego (out-of-box), która jest wprowadzana w Common Data Service wraz z integracją z programem Finance and Operations. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
VENDORACCOUNTNUMBER | = | msdyn\_vendoraccountnumber
VENDORGROUPID | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
VENDORORGANIZATIONNAME | = | msdyn\_name
VENDORPARTYTYPE | \>\< | msdyn\_isperson
PERSONFIRSTNAME | = | msdyn\_firstname
PERSONLASTNAME | = | msdyn\_lastname
CREDITLIMIT | = | msdyn\_vendorcreditlimit
ISFOREIGNENTITY | \>\< | msdyn\_isforeignentity
ISONETIMEVENDOR | \>\< | msdyn\_isonetimevendor
ADDRESSBUILDINGCOMPLIMENT | = | msdyn\_addressbuildingcompliment
PERSONCHILDRENNAMES | = | msdyn\_childrennames
ADDRESSCITY | = | msdyn\_addresscity
ADDRESSCOUNTRYREGIONID | = | msdyn\_addresscountryregionid
ADDRESSCOUNTRYREGIONISOCODE | = | msdyn\_addresscountryregionisocode
ADDRESSCOUNTYID | = | msdyn\_addresscountyid
CREDITRATING | = | msdyn\_creditrating
ADDRESSDESCRIPTION | = | msdyn\_addressdescription
ADDRESSDISTRICTNAME | = | msdyn\_addressdistrictname
DUNSNUMBER | = | msdyn\_dunsnumber
ETHNICORIGINID | = | msdyn\_ethnicorigin
FORMATTEDPRIMARYADDRESS | = | msdyn\_formattedprimaryaddress
PERSONHOBBIES | = | msdyn\_hobbies
PERSONINITIALS | = | msdyn\_initials
LANGUAGEID | = | msdyn\_languageid
PERSONLASTNAMEPREFIX | = | msdyn\_lastnameprefix
PERSONMIDDLENAME | = | msdyn\_middlename
ORGANIZATIONNUMBER | = | msdyn\_organizationnumber
OURACCOUNTNUMBER | = | msdyn\_ourvendoraccountnumber
PAYMENTID | = | msdyn\_paymentid
PERSONPHONETICFIRSTNAME | = | msdyn\_phoneticfirstname
PERSONPHONETICMIDDLENAME | = | msdyn\_phoneticmiddlename
PERSONPHONETICLASTNAME | = | msdyn\_phoneticlastname
ORGANIZATIONPHONETICNAME | = | msdyn\_organizationphoneticname
ADDRESSPOSTBOX | = | msdyn\_addresspostbox
PRIMARYURL | = | msdyn\_primarycontacturl
PRIMARYEMAILADDRESS | = | msdyn\_primaryemailaddress
PRIMARYEMAILADDRESSDESCRIPTION | = | msdyn\_primaryemailaddressdescription
PRIMARYFACEBOOK | = | msdyn\_primaryfacebook
PRIMARYFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYFAXNUMBER | = | msdyn\_primaryfaxnumber
PRIMARYFAXNUMBERDESCRIPTION | = | msdyn\_primaryfaxnumberdescription
PRIMARYFAXNUMBEREXTENSION | = | msdyn\_primaryfaxnumberextension
PRIMARYLINKEDIN | = | msdyn\_primarylinkedin
PRIMARYLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescription
PRIMARYPHONENUMBER | = | msdyn\_pimaryphonenumber
PRIMARYPHONENUMBERDESCRIPTION | = | msdyn\_primaryphonenumberdescription
PRIMARYPHONENUMBEREXTENSION | = | msdyn\_primaryphonenumberextension
PRIMARYTELEX | = | msdyn\_primarytelex
PRIMARYTELEXDESCRIPTION | = | msdyn\_primarytelexdescription
PRIMARYTWITTER | = | msdyn\_primarytwitter
PRIMARYTWITTERDESCRIPTION | = | msdyn\_primarytwitterdescription
PRIMARYURLDESCRIPTION | = | msdyn\_primaryurldescription
PERSONPROFESSIONALSUFFIX | = | msdyn\_professionalsuffix
PERSONPROFESSIONALTITLE | = | msdyn\_professionatitle
ADDRESSSTATEID | = | msdyn\_addressstateid
ADDRESSSTREET | = | msdyn\_addressstreet
ADDRESSSTREETNUMBER | = | msdyn\_addressstreetnumber
VENDORKNOWNASNAME | = | msdyn\_vendorknownasname
ADDRESSZIPCODE | = | msdyn\_addresszipcode
DEFAULTPAYMENTDAYNAME | = | msdyn\_defaultpaymentdayname.msdyn\_name
DEFAULTPAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
DEFAULTPAYMENTTERMSNAME | = | msdyn\_paymentterms.msdyn\_name
HASONLYTAKENBIDS | \>\< | msdyn\_hasonlytakenbids
ISMINORITYOWNED | \>\< | msdyn\_isminorityowned
ISVENDORLOCALLYOWNED | \>\< | msdyn\_isvendorlocallyowned
ISSERVICEVETERANOWNED | \>\< | msdyn\_isserviceveteranowned
ISOWNERDISABLED | \>\< | msdyn\_ownerisdisabled
ISWOMANOWNER | \>\< | msdyn\_womanowner
PERSONANNIVERSARYDAY | = | msdyn\_personanniversaryday
PERSONANNIVERSARYYEAR | = | msdyn\_anniversaryyear
PERSONBIRTHDAY | = | msdyn\_birthday
PERSONBIRTHYEAR | = | msdyn\_birthyear
ORGANIZATIONEMPLOYEEAMOUNT | = | msdyn\_numberofemployees
VENDORHOLDRELEASEDATE | = | msdyn\_vendoronholdreleasedate
VENDORPARTYNUMBER | = | msdyn\_vendorpartynumber
ADDRESSLOCATIONID | = | msdyn\_addresslocationid
PERSONANNIVERSARYMONTH | = | msdyn\_vendorpersonanniversarymonth
PERSONBIRTHMONTH | = | msdyn\_vendorpersonbirthmonth
PERSONMARITALSTATUS | \>\< | msdyn\_maritalstatus
ADDRESSLATITUDE | \>\> | msdyn\_addresslatitude
ADDRESSLONGITUDE | \>\> | msdyn\_addresslongitude
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
CURRENCYCODE | = | msdyn\_currencycode.isocurrencycode
ISVENDORLOCATEDINHUBZONE | \>\< | msdyn\_isvendorlocatedinhubzone
DEFAULTVENDORPAYMENTMETHODNAME | = | msdyn\_vendorpaymentmethod.msdyn\_name
INVOICEVENDORACCOUNTNUMBER | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
PERSONGENDER | \>\< | msdyn\_gender
AREPRICESINCLUDINGSALESTAX | \>\< | msdyn\_priceincludessalestax
SALESTAXGROUPCODE | = | msdyn\_taxgroup.msdyn\_name
VENDORPRICETOLERANCEGROUPID | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Kontakty

Ten szablon synchronizuje wszystkie podstawowe, drugorzędne i trzeciorzędne dane kontaktowe zarówno dla odbiorców, jak i dla dostawców, między programami Finance and Operations i Customer Engagement. Aby uzyskać szczegółowe informacje na temat mapowania encji, zobacz temat [Zintegrowane dane główne odbiorcy](dual-write-customer.md#contacts).

## <a name="vendor-groups"></a>Grupy dostawców

Ten szablon synchronizuje informacje o grupach dostawców między programami Finance and Operations i Customer Engagement.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
DEFAULTPAYMENTTERMNAME | = | msdyn\_paymentterms.msdyn\_name
OPIS | = | msdyn\_description
VENDORGROUPID | = | msdyn\_vendorgroup
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Metoda płatności dostawcy

Ten szablon synchronizuje informacje o metodzie płatności dostawcy między programami Finance and Operations i Customer Engagement.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAZWA | = | msdyn\_name
OPIS | = | msdyn\_description
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
ALLOWPAYMENTCOPIES | \>\< | msdyn\_allowpaymentcopies
PAYMENTTYPE | \>\< | msdyn\_paymenttype
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
ACCOUNTTYPE | \>\< | msdyn\_accounttype
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingposting
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_postdatedcheckclearingposting
PROMISSORYNOTEDRAFTTYPE | \>\< | msdyn\_promissorynotedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

