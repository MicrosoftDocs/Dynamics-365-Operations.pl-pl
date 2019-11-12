---
title: Zintegrowane dane główne odbiorcy
description: W tym temacie opisano integrację danych klienta między programami Finance and Operations i Common Data Service.
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
ms.openlocfilehash: a66beb6338ea593247c79a11feb7f301d56f32a9
ms.sourcegitcommit: 6e0909e95f38b7487a4b7f68cc62b723f8b59bd4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572525"
---
# <a name="integrated-customer-master"></a>Zintegrowane dane główne odbiorcy

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Jest to typowe dla rekordów klientów, które mają być danymi głównymi w więcej niż jednej aplikacji. Na przykład sprzedaż może przekazywać rekordy klientów komercyjnych za pośrednictwem aplikacji , a handel elektroniczny lub sprzedaż detaliczna mogą przekazywać rekordy klienta za pośrednictwem aplikacji Finance and Operations. Niezależnie od tego, skąd pochodzi rekord klienta, jest on integrowany w tle w graniach wszystkich aplikacji i niezależnie od różnic w infrastrukturze. Zintegrowane tworzenie danych głównych klienta pomaga obsługiwać scenariusze wielowątkowego tworzenia danych głównych i zapewnia kompleksowy widok klienta w pakiecie aplikacji Dynamics 365.

## <a name="customer-data-flow"></a>Przepływ danych klienta

*Odbiorca* jest dobrze zdefiniowaną koncepcją w aplikacjach. W związku z tym integracja danych odbiorcy polega tylko na ujednoliceniu koncepcji odbiorcy między dwoma aplikacjami. Ilustracja poniżej przedstawia przepływ danych klienta.

![Przepływ danych klienta](media/dual-write-customer-data-flow.png)

Klienci mogą być szeroko klasyfikowani według dwóch typów: klienci komercyjni/organizacyjni oraz konsumenci/użytkownicy końcowi. Te dwa typy klientów są przechowywane i przetwarzane w różny sposób w programach Finance and Operations i Common Data Service.

W programie Finance and Operations zarówno klienci komercyjni/organizacyjni, jak i konsumenci/użytkownicy końcowi są ustawieni jako dane główne w jednej tabeli o nazwie **CustTable** (CustomerCustomerV3Entity) i są klasyfikowani na podstawie atrybutu **Typ**. (Jeśli **Typ** jest ustawiony na **Organizacja**, klient jest klientem komercyjnym/organizacyjnym, a jeśli **Typ** jest ustawiony na **Osoba**, klient jest konsumentem/użytkownikiem końcowym). Informacje o podstawowej osobie kontaktowej są obsługiwana przez obiekt SMMContactPersonEntity.

W programie Common Data Service klienci komercyjnych/organizacyjnych są zapisywani jako dane główne w obiekcie Konto i są identyfikowani jako klienci, gdy atrybut **RelationshipType** jest ustawiony na **Klient**. Zarówno konsumenci/użytkownicy końcowi, jak i osoby kontaktowe są reprezentowane przez obiekt Contact. Aby zapewnić wyraźne oddzielenie konsumenta/użytkownika końcowego i osoby kontaktowej, obiekt **Contact** ma flagę logiczną o nazwie **Sellable**. Gdy **Sellable** ma wartość **True**, kontakt jest konsumentem/użytkownikiem końcowym, a oferty i zamówienia mogą być tworzone dla tego kontaktu. Gdy **Sellable** ma wartość **False**, kontakt jest tylko podstawową osobą kontaktowa klienta.

Gdy kontakt non-sellable uczestniczy w ofercie lub procesie zamówienia, flaga **Sellable** ma wartość **True**, aby oznaczyć kontakt jako sellable. Kontakt, który stał się kontaktem sellable pozostaje kontaktem sellable.

## <a name="templates"></a>Szablony

Dane klienta obejmują wszystkie informacje o kliencie, takie jak grupa odbiorców, adresy, dane kontaktowe, profil płatności, profil faktury i stan lojalności. Kolekcja mapy jednostki działa razem podczas interakcji z danymi klienta, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations    | Inne aplikacje w usłudze Dynamics 365
--------------------------|---------------------------------
Numer V3 odbiorcy               | Konto
Numer V3 odbiorcy               | Osoba kontaktowa
CDS Contacts wer. 2           | Osoba kontaktowa
Grupy odbiorców           | Msdyn\_customergroups
Metoda płatności odbiorcy   | Msdyn\_customerpaymentmethods
Karta lojalnościowa              | Msdyn\_loyaltycards
Harmonogram płatności          | Msdyn\_paymentschedules
Harmonogram płatności          | Msdyn\_paymentschedulelines
Dzień zapłaty w usłudze CDS           | Msdyn\_paymentdays
Wiersze dni zapłaty w usłudze CDS     | Msdyn\_paymentdaylines
Warunki płatności          | Msdyn\_paymentterms
Afiksy nazwy              | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="customer-v3-to-account"></a>Odbiorca (wersja 3) na Konto

Ten szablon synchronizuje dane główne odbiorcy dla klientów komercyjnych i organizacji między aplikacjami Finance and Operations i Common Data Service.

<!-- ![](media/dual-write-account-1.png) -->

<!-- ![](media/dual-write-account-2.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CUSTOMERACCOUNT | = | accountnumber
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
CREDITLIMIT | = | creditlimit
DELIVERYADDRESSCITY | = | address1\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
DELIVERYADDRESSCOUNTY | = | address1\_county
DELIVERYADDRESSLATITUDE | \> | address1\_latitude
DELIVERYADDRESSLONGITUDE | \> | address1\_longitude
DELIVERYADDRESSZIPCODE | = | address1\_postalcode
ORGANIZATIONNAME | = | name
ORGANIZATIONNUMBEROFEMPLOYEES | = | numberofemployees
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTTWITTER | = | primarytwitterid
PRIMARYCONTACTURL | = | websiteurl
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | opis
CREDITLIMITISMANDATORY | \>\< | msdyn\_creditlimitismandatory
CREDITRATING | = | msdyn\_creditrating
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
INVOICEACCOUNT | = | msdyn\_billingaccount.accountnumber
INVOICEADDRESS | \>\< | msdyn\_invoiceaddress
ISONETIMECUSTOMER | \>\< | msdyn\_onetimecustomer
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PAYMENTDAY | = | msdyn\_paymentday.msdyn\_name
PAYMENTMETHOD | = | msdyn\_customerpaymentmethod.msdyn\_name
PAYMENTSCHEDULE | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTTERMS | = | msdyn\_paymentterm.msdyn\_name
PAYMENTTERMSBASEDAYS | = | msdyn\_paymenttermsbasedays
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
PRIMARYCONTACTLINKEDIN | = | msdyn\_primarylinkedinid
TAXEXEMPTNUMBER | = | msdyn\_taxexemptnumber
VENDORACCOUNT | = | msdyn\_vendor.msdyn\_vendoraccountnumber
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
LANGUAGEID | \<\< | brak
DELIVERYADDRESSSTREET | = | address1\_line1
DELIVERYADDRESSSTATE | = | address1\_stateorprovince
brak | \>\> | address1\_addresstypecode
brak | \>\> | customertypecode
PARTYTYPE | \<\< | brak
PARTYNUMBER | = | msdyn\_partynumber

## <a name="customer-v3-to-contact"></a>Odbiorcy (wersja 3) na Kontakt

Ten szablon synchronizuje dane główne odbiorcy dla klientów i użytkowników końcowych między aplikacjami Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-contact-1.png) -->
<!-- ![](media/dual-write-contact-2.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
brak | \>\> | msdyn\_sellable
PARTYTYPE | \<\< | brak
PARTYNUMBER | = | msdyn\_partynumber
CUSTOMERACCOUNT | = | msdyn\_contactpersonid
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
PERSONFIRSTNAME | = | firstname
PERSONLASTNAME | = | lastname
PERSONMIDDLENAME | = | middlename
PERSONPROFESSIONALTITLE | = | jobtitle
PERSONGENDER | \>\< | gendercode
PERSONMARITALSTATUS | \>\< | familystatuscode
LANGUAGEID | \<\< | brak
ADDRESSCITY | = | address1\_city
ADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
ADDRESSCOUNTY | = | address1\_county
ADDRESSLATITUDE | \> | address1\_latitude
ADDRESSLONGITUDE | \> | address1\_longitude
ADDRESSLOCATIONROLES | \<\< | brak
ADDRESSSTATE | = | address1\_stateorprovince
ADDRESSSTREET | = | address1\_line1
ADDRESSZIPCODE | = | address1\_postalcode
ADDRESSPOSTBOX | = | address1\_postofficebox
brak | \>\> | address1\_addresstypecode
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
brak | \>\> | address2\_addresstypecode
DELIVERYADDRESSCITY | = | address3\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3\_country
DELIVERYADDRESSCOUNTY | = | address3\_county
DELIVERYADDRESSLATITUDE | \> | address3\_latitude
DELIVERYADDRESSLONGITUDE | \>\> | address3\_longitude
DELIVERYADDRESSSTATE | = | address3\_stateorprovince
DELIVERYADDRESSSTREET | = | address3\_line1
DELIVERYADDRESSZIPCODE | = | address3\_postalcode
brak | \>\> | address3\_addresstypecode
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTLINKEDIN | = | msdyn\_primaryinkedinid
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTER | = | msdyn\_primarytwitterid
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURL | = | websiteurl
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | opis

## <a name="contacts"></a>Kontakty

Ten szablon synchronizuje wszystkie podstawowe, drugorzędne i trzeciorzędne dane kontaktowe zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-contacts.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn\_partynumber
ASSOCIATEDCONTACTTYPE | \<\< | brak
FIRSTNAME | = | firstname
MIDDLENAME | = | middlename
LASTNAME | = | lastname
ASSOCIATEDCONTACTNUMBER | = | msdyn\_vendorcontactid.msdyn\_vendoraccountnumber
PRIMARYADDRESSCITY | = | address1\_city
PRIMARYADDRESSCOUNTRYREGIONID | = | address1\_country
PRIMARYADDRESSCOUNTYID | = | address1\_county
PRIMARYFAXNUMBER | = | fax
PRIMARYADDRESSSTATEID | = | address1\_stateorprovince
PRIMARYADDRESSSTREET | = | address1\_line1
PRIMARYADDRESSZIPCODE | = | address1\_postalcode
PRIMARYPHONENUMBER | = | telephone1
PRIMARYEMAILADDRESS | = | emailaddress1
EMPLOYMENTDEPARTMENT | = | department
NOTES | = | opis
GENDER | \>\< | gendercode
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid
PRIMARYURL | = | websiteurl
MARITALSTATUS | \>\< | familystatuscode
ISRECEIVINGDIRECTMAIL | \>\< | donotemail
EMPLOYMENTPROFESSION | = | jobtitle
SPOUSENAME | = | spousesname
brak | \>\> | msdyn\_contactforvendor
brak | \>\> | msdyn\_contactpersonid

## <a name="customer-groups"></a>Grupy odbiorców

Ten szablon synchronizuje informacje o grupach odbiorców między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-customer-groups.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CUSTOMERGROUPID | = | msdyn\_groupid
OPIS | = | msdyn\_description
ISSALESTAXINCLUDEDINPRICE | \>\< | msdyn\_issalestaxincludedinprice
PAYMENTTERMID | = | msdyn\_paymenttermid.msdyn\_name
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymenttermname.msdyn\_name

## <a name="customer-payment-methods"></a>Metoda płatności odbiorcy

Ten szablon synchronizuje informacje o metodach płatności odbiorców między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-customer-payment-methods.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAZWA | = | msdyn\_name
ACCOUNTTYPE | \>\< | msdyn\_accounttype
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingpostingenabled
ISSEPA | \>\< | msdyn\_issepa
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
OPIS | = | msdyn\_description
PAYMENTTYPE | \>\< | msdyn\_paymenttype
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | \>\< | msdyn\_invoiceupdate
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_enablepostdatescheckclearingposting
BILLOFEXCHANGEDRAFTTYPE | \>\< | msdyn\_billofexchangedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

## <a name="loyalty-cards"></a>Karty lojalnościowe

Ten szablon synchronizuje informacje kartach lojalnościowych odbiorców między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-loyalty-cards.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CARDNUMBER | = | msdyn\_cardnumber
CARDTENDERTYPE | \>\< | msdyn\_cardtendertype
PARTYNUMBER | = | msdyn\_partynumber
REPLACEMENTCARDNUMBER | \> | msdyn\_replacementcardnumber
OMOPERATINGUNITNUMBER | = | msdyn\_operatingunitnumber
LOYALTYENROLLMENTDATE | = | msdyn\_enrollmentdate

## <a name="payment-schedules"></a>Harmonogramy płatności

Ten szablon synchronizuje dane referencyjne harmonogramu płatności, zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-payment-schedules.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAZWA | = | msdyn\_name
OPIS | = | msdyn\_description
ALLOCATIONMETHOD | \>\< | msdyn\_allocationmethod
PAYMENTFREQUENCYUNITS | \>\< | msdyn\_paymentfrequencyunit
PAYMENTFREQUENCY | = | msdyn\_paymentfrequency
NUMBEROFPAYMENTS | = | msdyn\_numberofpayments
FIXEDPAYMENTAMOUNT | = | msdyn\_fixedpaymentamount
MINIMUMPAYMENTAMOUNT | = | msdyn\_minimumpaymentamount
SALESTAXALLOCATIONMETHOD | \>\< | msdyn\_salestaxallocationmethod
NOTES | = | msdyn\_note

## <a name="payment-schedule-lines"></a>Wiersze harmonogramu płatności

Synchronizuje wiersze referencyjne harmonogramu płatności, zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-payment-schedule-lines.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTSCHEDULENAME | \> | msdyn\_name
LINENUMBER | = | msdyn\_linenumber
PERIODSAFTERDUEDATE | = | msdyn\_periodsafterduedate
PERCENTORAMOUNT | \>\< | msdyn\_percentoramount
PERCENTORAMOUNTVALUE | = | msdyn\_percentoramountvalue

## <a name="payment-days"></a>Dni płatności

Ten szablon synchronizuje dane referencyjne dni płatności, zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-payment-days.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
NAZWA | = | msdyn\_name
OPIS | = | msdyn\_description

## <a name="payment-day-lines"></a>Wiersze dnia płatności

Ten szablon synchronizuje dane referencyjne dni wierszy płatności, zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-payment-day-lines.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CDSINTEGRATIONKEY | = | msdyn\_paymentdaylineid
FREQUENCY | \>\< | msdyn\_frequency
DAYOFWEEK | \>\< | msdyn\_dayofweek
DAYOFMONTH | = | msdyn\_dayofmonth
NAZWA | = | msdyn\_paymentday.msdyn\_name

## <a name="payment-terms"></a>Warunki płatności

Ten szablon synchronizuje dane referencyjne warunków płatności (warunki płatności), zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-payment-terms.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
OPIS | = | msdyn\_description
NAZWA | = | msdyn\_name
NUMBEROFMONTHS | = | msdyn\_numberofmonth
CUTOFFDAYOFMONTH | = | msdyn\_cutoffdayofmonth
ISCASHPAYMENT | \>\< | msdyn\_iscashpayment
NUMBEROFDAYS | = | msdyn\_days
ISCERTIFIEDCOMPANYCHECK | \>\< | msdyn\_iscertifiedcompanycheck
ISDEFAULTPAYMENTTERM | \>\< | msdyn\_isdefaultpaymentterm
CREDITCARDPAYMENTTYPE | \>\< | msdyn\_creditcardpaymenttype
CREDITCARDCREDITCHECKTYPE | \>\< | msdyn\_creditcardcreditchecktype
PAYMENTDAYNAME | = | msdyn\_paymentdayname.msdyn\_name
PAYMENTMETHODTYPE | \>\< | msdyn\_paymentmethodtype
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedulename.msdyn\_name

## <a name="name-affixes"></a>Afiksy nazwy

Ten szablon synchronizuje afiksów nazwy, zarówno dla odbiorców, jak i dla dostawców, między Finance and Operations i innymi aplikacjami Dynamics 365.

<!-- ![](media/dual-write-name-affixes.png) -->

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
AFFIX | = | msdyn\_affix
TYP | \>\< | msdyn\_affixtype
OPIS | = | msdyn\_description
