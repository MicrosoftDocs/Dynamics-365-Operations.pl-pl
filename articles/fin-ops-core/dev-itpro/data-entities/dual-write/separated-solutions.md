---
title: Osobny pakiet Aranżacja aplikacji Podwójny zapis
description: Pakiet Aranżacja aplikacji Podwójny zapis nie jest już pojedynczym pakietem, ale został rozdzielony na mniejsze pakiety. W tym artykule opisano rozwiązania i mapy, które zawiera każdy pakiet, oraz jego zależność od innych pakietów.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: 504939f1f98c18005c092cabc1d040b420402c93
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874820"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Osobny pakiet Aranżacja aplikacji Podwójny zapis

[!include [banner](../../includes/banner.md)]



Poprzednio pakiet Aranżacja aplikacji Podwójny zapis był jednym pakietem, który zawierał następujące rozwiązania:

- Dynamics 365 Notes
- Dynamics 365 Finance and Operations Common Anchor
- Mapy encji podwójnego zapisu rozwiązania Dynamics 365 Finance and Operations
- Aplikacja Dynamics 365 — Zarządzanie składnikami majątku
- Dynamics 365 — Zarządzanie składnikami majątku
- Funkcje wspólne modułu HCM
- Dynamics 365 Supply Chain Extended
- Dynamics 365 Finance Extended
- Dynamics 365 Finance and Operations Common
- Dynamics 365 Company
- Kursy wymiany walut
- Field Service Common

Był to pojedynczy pakiet, więc tworzył sytuację „wszystko albo nic” dla odbiorców. Jednak firma Microsoft rozdzieliła go na mniejsze pakiety. W związku z tym odbiorca może wybrać tylko pakiety potrzebnych mu rozwiązań. Na przykład jeśli jesteś odbiorcą używającym rozwiązania Microsoft Dynamics 365 Supply Chain Management i nie potrzebujesz integracji z rozwiązaniami Dynamics 365 Human Resources, Notes oraz Zarządzanie składnikami majątku, możesz wykluczyć te rozwiązania z instalowanych rozwiązań. Nazwy rozwiązań źródłowych, wydawca oraz mapy wersji pozostają takie same, więc ta zmiana nie powoduje przerwania instalacji. Istniejące instalacje można uaktualnić.

![Rozdzielony pakiet.](media/separated-package-1.png)

W tym artykule opisano rozwiązania i mapy, które zawiera każdy pakiet, oraz jego zależność od innych pakietów.

## <a name="dual-write-application-core"></a>Podstawowe funkcje aplikacji Podwójny zapis

Pakiet Podstawowe funkcje aplikacji Podwójny zapis umożliwia użytkownikom instalowanie i konfigurowanie aplikacji Podwójny zapis bez innych aplikacji platformy Customer Engagement. Ten pakiet zawiera pięć poniższych rozwiązań.

| Unikatowa nazwa                           | Nazwa wyświetlana                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 Company                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Finance and Operations Common |
| CurrencyExchangeRates                 | Kursy wymiany walut                    |
| msdyn_DualWriteAppCoreMaps            | Podstawowe funkcje aplikacji Podwójny zapis — mapy jednostek   |
| msdyn_DualWriteAppCoreAnchor          | Podstawowe funkcje aplikacji Podwójny zapis — zakotwiczenie        |

W tym pakiecie są dostępne następujące mapy.

| Aplikacje Finanse i Działania     | Aplikacje Customer Engagement                    |
|---------------------------------|---------------------------------------------|
| Jednostka operacyjna                  | msdyn_internalorganizations                 |
| Hierarchia organizacyjna          | msdyn_internalorganizationhierarchies       |
| Osoby prawne                  | msdyn_internalorganizations                 |
| Osoby prawne                  | cdm_companies                               |
| Cele hierarchii organizacji | msdyn_internalorganizationhierarchypurposes |
| Para walut kursu wymiany     | msdyn_currencyexchangeratepairs             |
| Afiksy nazwy                    | msdyn_nameaffixes                           |
| Typ kursu wymiany              | msdyn_exchangeratetypes                     |
| Kursy wymiany w usłudze CDS              | msdyn_currencyexchangerates                 |
| Typ hierarchii organizacyjnej     | msdyn_internalorganizationhierarchytypes    |
| Waluty                      | transactioncurrencies                       |
| Jednostka Przewodniki po technologii rzeczywistości mieszanej     | msmrw_guides                                |

**Informacje dotyczące zależności**

Pakiet Podstawowe funkcje aplikacji Podwójny zapis nie ma zależności od innych pakietów.

## <a name="dual-write-human-resources"></a>Human Resources — Podwójny zapis

Pakiet Human Resources — Podwójny zapis zawiera rozwiązania i mapy wymagane do synchronizacji danych modułu Human Resources. Ten pakiet zawiera trzy poniższe rozwiązania.

| Unikatowa nazwa                | Nazwa wyświetlana                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | Funkcje wspólne modułu HCM                               |
| msdyn_Dynamics365HCMMaps   | Dynamics 365 Human Resources — mapy jednostek |
| msdyn_Dynamics365HCMAnchor | Dynamics 365 Human Resources — zakotwiczenie      |

W tym pakiecie są dostępne następujące mapy.

| Aplikacje Finanse i Działania | Aplikacje Customer Engagement         |
|-----------------------------|----------------------------------|
| Pochodzenie etniczne              | cdm_ethnicorigins                |
| Wynagrodzenie — funkcja stanowiska   | cdm_jobfunctions                 |
| Stanowiska V2                | cdm_jobpositions                 |
| Stanowiska                        | cdm_jobs                         |
| Wynagrodzenie — typ stanowiska       | cdm_jobtypes                     |
| Kody języków              | cdm_languages                    |
| Typ stanowiska               | cdm_positiontypes                |
| Przypisania pracowników do stanowisk | cdm_positionworkerassignmentmaps |
| Status kombatanta              | cdm_veteranstatuses              |
| Pracownik                      | cdm_workers                      |
| Zatrudnienie według firmy      | cdm_employments                  |

**Informacje dotyczące zależności**

Pakiet Human Resources — Podwójny zapis jest zależny od pakietu Podstawowe funkcje aplikacji Podwójny zapis. Z tego powodu musisz zainstalować pakiet Podstawowe funkcje aplikacji Podwójny zapis, zanim zainstalujesz pakiet Human Resources — Podwójny zapis.

## <a name="dual-write-supply-chain"></a>Supply Chain — Podwójny zapis

Pakiet Supply Chain — Podwójny zapis zawiera rozwiązania i mapy wymagane do synchronizacji danych modułu Supply Chain Management. Ten pakiet zawiera trzy poniższe rozwiązania.

| Unikatowa nazwa                                | Nazwa wyświetlana                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain Extended                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Dynamics 365 Supply Chain Management — rozszerzone mapy jednostek |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Dynamics 365 Supply Chain Management — rozszerzone zakotwiczenie      |

W tym pakiecie są dostępne następujące mapy.

| Aplikacje Finanse i Działania                 | Aplikacje Customer Engagement                      |
|---------------------------------------------|-----------------------------------------------|
| Jednostki                                       | uoms                                          |
| Nagłówki zamówień sprzedaży CDS                     | salesorders                                   |
| Wiersze zamówienia sprzedaży CDS                       | salesorderdetails                             |
| Nagłówek oferty sprzedaży CDS                  | Cytaty                                        |
| Wiersze oferty sprzedaży CDS                   | quotedetails                                  |
| Odrębne produkty zwolnione w usłudze CDS              | produkty                                      |
| Strefy magazynowe                             | msdyn_warehousezones                          |
| Grupy stref magazynowych                       | msdyn_warehousezonegroups                     |
| Wiersze pracy magazynowej                        | msdyn_warehouseworklines                      |
| Nagłówki pracy magazynowej                      | msdyn_warehouseworkheaders                    |
| Magazyny                                  | msdyn_warehouses                              |
| Korytarz w magazynie                             | msdyn_warehouseaisles                         |
| Konwersje jednostek                            | msdyn_unitofmeasureconversions                |
| Warunki dostawy                           | msdyn_termsofdeliveries                       |
| Metody dostawy                           | msdyn_shipvias                                |
| Style produktu głównego                       | msdyn_sharedproductstyles                     |
| Wiersze faktur sprzedaży wer. 2                      | invoicedetails                                |
| Nagłówki faktur sprzedaży wer. 2                    | faktury                                      |
| Rozmiary produktu głównego                        | msdyn_sharedproductsizes                      |
| Zwolnione produkty (wersja 2)                        | msdyn_sharedproductdetails                    |
| Konfiguracje produktu głównego               | msdyn_sharedproductconfigurations             |
| Kolory produktu głównego                       | msdyn_sharedproductcolors                     |
| Kody źródeł zamówień sprzedaży                    | msdyn_salesorderorigins                       |
| Nagłówek dokumentu przyjęcia produktów                      | msdyn_purchaseorderreceipts                   |
| Wiersz dokumentu przyjęcia produktów                        | msdyn_purchaseorderreceiptproducts            |
| Nagłówki zamówień zakupu V2                   | msdyn_purchaseorders                          |
| Jednostka wstępnie usuniętego wiersza zamówienia zakupu usługi CDS | msdyn_purchaseorderproducts                   |
| Jednostka wiersza zamówienia zakupu w usłudze CDS              | msdyn_purchaseorderproducts                   |
| Grupy wymiarów śledzenia                   | msdyn_producttrackingdimensiongroups          |
| Style                                      | msdyn_productstyles                           |
| Grupy wymiarów magazynowania                    | msdyn_productstoragedimensiongroups           |
| Konwersje jednostek specyficzne dla produktu           | msdyn_productspecificunitofmeasureconversions |
| Ustawienia domyślne zamówienia produktu (wersja 2)           | msdyn_productspecificdefaultordersettings     |
| Rozmiary                                       | msdyn_productsizes                            |
| Grupy wymiarów produktu                    | msdyn_productdimensiongroups                  |
| Ustawienia domyślne zamówień                      | msdyn_productdefaultordersettings             |
| Konfiguracje                              | msdyn_productconfigurations                   |
| Wszystkie produkty                                | msdyn_globalproducts                          |
| Kolory                                      | msdyn_productcolors                           |
| Role hierarchii kategorii produktów            | msdyn_productcategoryhierarchyroles           |
| Hierarchie kategorii produktów                | msdyn_productcategoryhierarchies              |
| Przypisania kategorii produktów                | msdyn_productcategoryassignments              |
| Kategorie produktów                          | msdyn_productcategories                       |
| Lokalizacje w magazynach                         | msdyn_inventorylocations                      |
| Zapasy w usłudze CDS w                            | msdyn_inventoryonhandentries                  |
| Kategorie produktów                          | msdyn_productcategories                       |
| Zapasy w usłudze CDS w                            | msdyn_inventoryonhandrequests                 |
| Kod kreskowy identyfikujący numer produktu           | msdyn_productbarcodes                         |
| Karta lojalnościowa                                | msdyn_loyaltycards                            |
| Punkty lojalnościowe                       | msdyn_loyaltyrewardpoints                     |
| Grupy odbiorców ceny                       | msdyn_pricecustomergroups                     |
| Oddziały                                       | msdyn_operationalsites                        |
| Wiersze oferty sprzedaży CDS                   | quotedetails                                  |
| Wiersze zamówienia sprzedaży CDS                       | salesorderdetails                             |

**Informacje dotyczące zależności**

Pakiet Supply Chain — Podwójny zapis jest zależny od wymienionych poniżej trzech pakietów. Z tego powodu musisz zainstalować te pakiety, zanim zainstalujesz pakiet Supply Chain — Podwójny zapis.

- Pakiet Podstawowe funkcje aplikacji Podwójny zapis
- Pakiet Finance — Podwójny zapis
- Pakiet Human Resources — Podwójny zapis

## <a name="dual-write-finance"></a>Finance — Podwójny zapis

Pakiet Finance — Podwójny zapis zawiera rozwiązania i mapy wymagane do synchronizacji danych rozwiązania Dynamics 365 Finance. Ten pakiet zawiera cztery poniższe rozwiązania.

| Unikatowa nazwa                            | Nazwa wyświetlana                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Rozszerzone mapy jednostek usługi Dynamics 365 Finance |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Rozszerzona kotwica systemu Dynamics 365 Finance      |

W tym pakiecie są dostępne następujące mapy.

| Aplikacje Finanse i Działania             | Aplikacje Customer Engagement        |
|-----------------------------------------|---------------------------------|
| Grupy potrąconych zaliczek na podatek                  | msdyn_withholdingtaxgroups      |
| Kontakty w usłudze CDS w wersji 2 (odbiorca)              | kontakty                        |
| Kontakty w usłudze CDS w wersji 2 (dostawca)                | kontakty                        |
| Odbiorcy (wersja 3)                            | kontakty                        |
| Kody potrąconych zaliczek na podatek                   | msdyn_withholdingtaxcodes       |
| Dostawcy V2                              | msdyn_vendors                   |
| Metoda płatności dostawcy                   | msdyn_vendorpaymentmethods      |
| Grupy dostawców                           | msdyn_vendorgroups              |
| Plan kont                       | msdyn_chartofaccountses         |
| Grupy V2 księgowania podatku w księdze      | msdyn_taxpostinggroups          |
| Grupa podatków dla pozycji                    | msdyn_taxitemgroups             |
| Grupy podatków                        | msdyn_taxgroups                 |
| Jednostka Kod zwolnienia z podatku w usłudze CDS        | msdyn_taxexemptcodes            |
| Grupy odbiorców                         | msdyn_customergroups            |
| Metoda płatności odbiorcy                 | msdyn_customerpaymentmethods    |
| Wymiary finansowe                    | msdyn_dimensionattributes       |
| Urzędy skarbowe                   | msdyn_taxauthorities            |
| Format wymiaru finansowego              | msdyn_financialdimensionformats |
| Kalendarzowy okres obrachunkowy                  | msdyn_fiscalcalendarperiods     |
| Jednostka Integracja kalendarza obrachunkowego      | msdyn_fiscalcalendars           |
| Jednostka Integracja roku kalendarza obrachunkowego | msdyn_fiscalcalendaryears       |
| Warunki płatności                        | msdyn_paymentterms              |
| Harmonogram płatności                        | msdyn_paymentschedules          |
| Wiersze harmonogramu płatności                  | msdyn_paymentschedulelines      |
| Dni zapłaty w usłudze CDS                        | msdyn_paymentdays               |
| Wiersze dni zapłaty w usłudze CDS wer. 2                | msdyn_paymentdaylines           |
| Konto główne                            | msdyn_mainaccounts              |
| Kategorie kont głównych                 | msdyn_mainaccountcategories     |
| Ledger                                  | msdyn_ledgers                   |
| Odbiorcy (wersja 3)                            | Konta                        |

**Informacje dotyczące zależności**

Pakiet Finance — Podwójny zapis jest zależny od pakietu Podstawowe funkcje aplikacji Podwójny zapis. Z tego powodu musisz zainstalować pakiet Podstawowe funkcje aplikacji Podwójny zapis, zanim zainstalujesz pakiet Finance — Podwójny zapis.

## <a name="dual-write-notes"></a>Notes — Podwójny zapis

Pakiet Notes — Podwójny zapis zawiera rozwiązania i mapy wymagane do synchronizacji danych uwag lub adnotacji. Ten pakiet zawiera cztery poniższe rozwiązania.

| Unikatowa nazwa                  | Nazwa wyświetlana                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 Notes             |
| Dynamics365NotesExtended     | Dynamics 365 Notes — funkcje rozszerzone    |
| msdyn_Dynamics365NotesMaps   | Dynamics 365 Notes — mapy jednostek |
| msdyn_Dynamics365NotesAnchor | Dynamics 365 Notes — zakotwiczenie      |

W tym pakiecie są dostępne następujące mapy.

| Finanse i Działania                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Załączniki dokumentu nagłówka zamówienia sprzedaży    | adnotacje         |
| Załączniki odbiorcy                       | adnotacje         |
| Załączniki dokumentów dostawców                | adnotacje         |
| Załączniki dokumentu nagłówka zamówienia zakupu | adnotacje         |

**Informacje dotyczące zależności**

Pakiet Notes — Podwójny zapis jest zależny od wymienionych poniżej dwóch pakietów. Z tego powodu musisz zainstalować te pakiety, zanim zainstalujesz pakiet Notes — Podwójny zapis.

- Pakiet Podstawowe funkcje aplikacji Podwójny zapis
- Pakiet Finance — Podwójny zapis

## <a name="dual-write-asset-management"></a>Zarządzanie składnikami majątku — Podwójny zapis

Pakiet Zarządzanie składnikami majątku — Podwójny zapis zawiera rozwiązania i mapy wymagane do synchronizacji danych składników aktywów z modułu Supply Chain Management lub rozwiązania Dynamics 365 Field Service. Ten pakiet zawiera cztery poniższe rozwiązania.

| Unikatowa nazwa                          | Nazwa wyświetlana                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 — Zarządzanie składnikami majątku             |
| Dynamics365AssetManagementApp        | Aplikacja Dynamics 365 — Zarządzanie składnikami majątku          |
| msdyn_DualWriteAssetManagementMaps   | Dynamics 365 — Zarządzanie składnikami majątku — mapy jednostek |
| msdyn_DualWriteAssetManagementAnchor | Dynamics 365 — Zarządzanie składnikami majątku — zakotwiczenie      |

W tym pakiecie są dostępne następujące mapy.

| Aplikacje Finanse i Działania                           | Aplikacje Customer Engagement                |
|-------------------------------------------------------|-----------------------------------------|
| Gwarancja zarządzania składnikami majątku                             | msdyn_warranties                        |
| Modele zarządzania składnikami majątku                               | msdyn_models                            |
| Producenci zarządzania składnikami majątku                        | msdyn_manufacturers                     |
| Typy lokalizacji czynności konserwacyjnych zarządzania składnikami majątku            | msdyn_functionallocationtypes           |
| Lokalizacje czynności konserwacyjnych zarządzania składnikami majątku                 | msdyn_functionallocations               |
| Stany cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn_functionallocationlifecyclestates |
| Modele cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn_functionallocationlifecyclemodels |
| Składniki majątku zarządzania składnikami majątku                               | msdyn_customerassets                    |
| Typy składników majątku zarządzania składnikami majątku                          | msdyn_customerassetcategories           |
| Stany cyklu życia składnika majątku zarządzania składnikami majątku               | msdyn_assetlifecyclestates              |
| Modele cyklu życia składnika majątku zarządzania składnikami majątku               | msdyn_assetlifecyclemodels              |

**Informacje dotyczące zależności**

Pakiet Zarządzanie składnikami majątku — Podwójny zapis jest zależny od pakietu Podstawowe funkcje aplikacji Podwójny zapis. Z tego powodu musisz zainstalować pakiet Podstawowe funkcje aplikacji Podwójny zapis, zanim zainstalujesz pakiet Zarządzanie składnikami majątku — Podwójny zapis.

## <a name="packages-required-for-project-operations"></a>Pakiety wymagane dla rozwiązania Project Operations
Rozwiązanie Project Operations jest zależne od wymienionych poniżej pakietów. Z tego powodu musisz zainstalować te pakiety, zanim zainstalujesz rozwiązanie Project Operations.

- Pakiet Podstawowe funkcje aplikacji Podwójny zapis
- Pakiet Finance — Podwójny zapis
- Pakiet Supply Chain — Podwójny zapis
- Pakiet Zarządzanie składnikami majątku — Podwójny zapis
- Pakiet Human Resources — Podwójny zapis

## <a name="dual-write-party-and-global-address-book-solutions"></a>Zainstaluj rozwiązania z podwójnym zapisem i globalna książka adresowa

Pakiet dwu write party i globalna książka adresowa zawiera następujące rozwiązania i mapy, które są wymagane do synchronizacji strony i globalna książka adresowa danych. 

| Unikatowa nazwa                       | Nazwa wyświetlana                            |
|-----------------------------------|-----------------------------------------|
| Strona                             | Strona                                   |
| Dynamics365GABExtended            | Dynamics 365 GAB Extended               |
| Dynamics365GABDualWriteEntityMaps | Dynamics 365 GAB Mapy jednostek podwójnego zapisu |
| Dynamics365GABParty_Anchor        | Dynamics 365 GAB i strona              |

W tym pakiecie są dostępne następujące mapy.

| Aplikacje Finanse i Działania | Aplikacje Customer Engagement | 
|-----------------------------|--------------------------|
| Strony usługi CDS | msdyn_parties | 
| Lokalizacje adresu pocztowego usługi CDS | msdyn_postaladdresscollections | 
| Historia adresu pocztowego usługi CDS V2 | msdyn_postaladdresses | 
| Lokalizacje adresu pocztowego strony usługi CDS | msdyn_partypostaladdresses | 
| Osoby kontaktowe strony wer. 3 | msdyn_partyelectronicaddresses | 
| Odbiorcy (wersja 3) | Konta | 
| Odbiorcy (wersja 3) | kontakty | 
| Dostawcy V2 | msdyn_vendors | 
| Tytuły osoby kontaktowej | msdyn_salescontactpersontitles | 
| Formuły grzecznościowe | msdyn_complimentaryclosings | 
| Zwroty grzecznościowe | msdyn_salutations | 
| Role podejmujące decyzje | msdyn_decisionmakingroles | 
| Funkcje stanowisk zatrudnienia | msdyn_employmentjobfunctions | 
| Poziomy lojalności | msdyn_loyaltylevels | 
| Typy osób | msdyn_personalcharactertypes | 
| Osoby kontaktowe (wersja 2) | msdyn_contactforparties | 
| Nagłówek oferty sprzedaży CDS | Cytaty | 
| Nagłówki zamówień sprzedaży CDS | salesorders | 
| Nagłówki faktur sprzedaży wer. 2 | faktury | 
| Role adresów CDS | msdyn_addressroles |

**Informacje dotyczące zależności**

Rozwiązania typu dwu-write party i globalna książka adresowa zależą od następujących trzech pakietów. Dlatego te pakiety należy zainstalować przed zainstalowaniem pakietu rozwiązań podwójnego zapisu i globalnej książki adresowej.

- Pakiet Podstawowe funkcje aplikacji Podwójny zapis
- Pakiet Finance — Podwójny zapis
- Pakiet Supply Chain — Podwójny zapis
