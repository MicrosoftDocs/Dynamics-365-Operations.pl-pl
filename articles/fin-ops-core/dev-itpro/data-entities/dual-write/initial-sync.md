---
title: Łańcuch zależności jednostek (kolejność synchronizacji)
description: W tym temacie opisano kolejność synchronizacji obowiązującą podczas tworzenia danych początkowych.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: 9ae14703941b97308bca5845eeac3eb9b181ae75
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275494"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Łańcuch zależności jednostek (kolejność synchronizacji)

[!include [banner](../../includes/banner.md)]

W tym temacie określono kolejność synchronizacji, którą należy wykonywać, aby utworzyć początkowe dane, jeśli nie są używane zależności jednostek określone przez funkcję **Wstępnej synchronizacji**. Jeśli nie jest używana **synchronizacja wstępna**, poszczególne mapowania jednostek należy uruchamiać pojedynczo.

## <a name="dynamics-365-supply-chain-management-entities"></a>Jednostki usługi Dynamics 365 Supply Chain Management

Poniżej znajdują się jednostki dla Supply Chain Management w kolejności, w jakiej należy je włączyć.

| Nazwa mapowania na stronie podwójnego zapisu | Nazwa metadanych jednostki w Supply Chain Management | Nazwa metadanych jednostki w Common Data Service | Notatki |
|---|---|---|---|
| Jednostki ... do uoms                                                                      | UnitOfMeasureEntity                                    | uom                                          | |
| Konwersje jednostek ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Wszystkie produkty ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Grupy wymiarów produktu ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Grupy wymiarów magazynowania ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Grupy wymiarów śledzenia ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Kolory ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Rozmiary ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Style ... msdyn_productstyles                                                      | EcoResProductStyleEntity                               | msdyn_productstyle                           | |
| Konfiguracje ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Wydane produkty (wersja 2) ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Common Data Service zwalnia odrębne produkty ... products                         | EcoResReleasedDistinctProductCommon Data ServiceEntity | produkt                                      | |
| Identyfikator produktu jako kod kreskowy ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Ustawienia domyślne zamówienia ... msdyn_productdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Ustawienia domyślne zamówień produktów (wersja 2) ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Konwersje jednostek specyficzne dla produktu ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Witryny ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Magazyny ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Zobacz [uwaga 1](#scm-notes). |
| Kolory produktu głównego ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Rozmiary produktu głównego ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Style produktu głównego ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Konfiguracje produktu głównego ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Kategorie produktów ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategorie                        | Zobacz [uwaga 2](#scm-notes). |
| Przypisania kategorii produktów ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Hierarchie kategorii produktów ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchie               | |
| Role hierarchii kategorii produktów ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Korytarz w magazynie... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Strefy magazynowe do msdyn_warehousezones                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Grupy stref magazynowych ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Lokalizacje magazynów ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Zobacz [uwaga 3](#scm-notes). |
| Nagłówki pracy magazynowej ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Wiersze pracy magazynowej ... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Zobacz [uwaga 4](#scm-notes). |
| Metody dostawy ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Warunki dostawy ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Kody pochodzenia zamówień sprzedaży ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| Nagłówki zamówień sprzedaży Common Data Service ... salesorders                             | SalesOrderHeaderCommon Data ServiceEntity              | salesorder                                   | |
| Wiersze zamówienia sprzedaży Common Data Service ... salesorderdetails                         | SalesOrderLineCommon Data ServiceEntity                | salesorderdetails                            | |
| Nagłówek oferty sprzedaży Common Data Service ... quotes                               | SalesQuotationHeaderCommon Data ServiceEntity          | oferta                                        | |
| Wiersze oferty sprzedaży Common Data Service ... quotedetails                          | SalesQuotationLineCommon Data ServiceEntity            | QuoteDetails                                 | |
| Nagłówki faktur sprzedaży wer. 2 ... invoices                                               | SalesInvoiceHeaderV2Entity                             | faktura                                      | |
| Wiersze faktur sprzedaży wer. 2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Informacje dotyczące mapowania

1. Ze względu na własne zależności konieczne może być uruchomienie synchronizacji początkowej dwa razy.
2. Domyślnie synchronizacja początkowa jest wyłączona z powodu relacji nadrzędny-podrzędny („inteligentna” kolejność nie jest obsługiwana przez platformę). Dlatego istniejące kategorie produktów muszą być synchronizowane ręcznie (na przykład przez zaktualizowanie opisu kategorii) w poprawnym zamówieniu (kategoria główna, następnie elementy podrzędne, a następnie dzieci podrzędne). Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Ustawienia \> Kategorie i atrybuty \> Hierarchie kategorii**. Na stronie **Hierarchie kategorii** można wybrać każdą hierarchię i wyświetlić odpowiednie kategorie produktów.
3. Mapowanie pustych pól wyszukiwania **ItemNumberInLocation** i pierwszej, drugiej i trzeciej dodatkowej strefy magazynowania spowoduje niepowodzenie synchronizacji początkowej. Dlatego te mapowania są teraz usuwane.
4. Mapowanie pustego pola **CaptureWeight** spowoduje niepowodzenie synchronizacji początkowej. Dlatego to mapowanie jest teraz usunięte.

### <a name="setup-related-information"></a>Informacje powiązane z konfiguracją

+ Po utworzeniu rekordów w jednostce **Produkty** w aplikacjach opartych na modelu w Dynamics 365 są one w stanie **Wersja robocza**. Aby zmienić status na **Aktywny** przejdź do **Ustawienia \> Administracja \> Ustawienia systemu \> Sprzedaż** w aplikacji opartej na modelu i ustaw opcję **Utwórz produkty w stanie aktywnym** na **Tak**.
+ Jeśli rekordy są tworzone w jednostce **Produkty** w aplikacjach opartych na modelach w Dynamics 365 lub w Common Data Service przed włączeniem podwójnego zapisywania, rekordy te będą aktualizowane tylko wtedy, gdy cały klucz, w tym **Firma**, zgadza się z danymi w aplikacji Finance and Operations.
+ Synchronizacja jednostki **Produkty** jest jednokierunkowe, od aplikacji Finance and Operations do Common Data Service. Jeśli mapowane pole w jednostce **Produkty** w aplikacji w Dynamics 365 jest aktualizowane, aktualizacja zostanie zastąpiona podczas następnej synchronizacji z poziomu aplikacji Finance and Operations.

### <a name="known-issues"></a>Znane problemy

- Błąd występuje w przypadku usunięcia jednostki w aplikacji Finance and Operations. Gdy jednostki miary zostaną zsynchronizowane z poziomu aplikacji Finance and Operations do Common Data Service, pierwsza jednostka określonej klasy zostanie utworzona jako jednostka podstawowa i uniemożliwi usunięcie.

    **Łagodzenie:** najpierw usuń jednostkę w Common Data Service. Można go następnie usunąć w aplikacji Finance and Operations.

- Błąd występuje po usunięciu witryny operacyjnej w aplikacji Common Data Service. Komunikat o błędzie stanu, „Dziennik: Ostrzeżenie: adres podstawowy nie może zostać usunięty.; Ostrzeżenie: nie można usunąć rekordu jednostki, ponieważ weryfikacja nie powiodła się dla następującego źródła danych: InventSiteLogisticsLocation (InventSiteLogisticsLocation).” Ten błąd jest spowodowany problemem w jednostce danych w aplikacji Finance and Operations.

    **Łagodzenie:** możesz usunąć witrynę w aplikacji Finance and Operations. Witryna zostanie wówczas usunięta w Common Data Service, jeśli jest uruchomiona odpowiednia mapa podwójnego zapisywania.

## <a name="dynamics-365-finance-entities"></a>Jednostki usługi Dynamics 365 Finance

Następujące jednostki w Dynamics 365 Finance są wymienione w kolejności, w której należy je włączyć.

| Nazwa mapowania na stronie podwójnego zapisu | Nazwa metadanych jednostki w Finance | Nazwa metadanych jednostki w Common Data Service | Notatki |
|---|---|---|---|
| Waluty ... transactioncurrencies                                            | CurrencyEntity                              | Waluta                                   | |
| Typ kursu wymiany ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Para walut kursu wymiany ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Kursy wymiany Common Data Service ... msdyn_currencyexchangerates              | ExchangeRateCommon Data ServiceEntity       | msdyn_currencyexchangerate                 | Zobacz [uwaga 1](#fin-notes). |
| Jednostka integracji kalendarza obrachunkowego ... msdyn_fiscalcalendars                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Jednostka integracji roku kalendarza obrachunkowego ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Okres kalendarza obrachunkowego ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Typ hierarchii organizacyjnej ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Zobacz [uwaga 1](#fin-notes). |
| Cele hierarchii organizacyjnej ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Zobacz [uwaga 1](#fin-notes). |
| Firmy ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Zobacz [uwaga 1](#fin-notes). |
| Firmy ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Jednostka operacyjna ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Zobacz [uwaga 1](#fin-notes). |
| Hierarchia organizacyjna — opublikowana ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Zobacz [uwaga 1](#fin-notes). |
| Afiksy nazw ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Dni płatności Common Data Service ... msdyn_paymentdays                          | PaymentDayCommon Data ServiceEntity         | msdyn_paymentday                           | |
| Wiersze dni płatności Common Data Service wersja 2 ... msdyn_paymentdaylines              | PaymentDayLineCommon Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Harmonogramy płatności ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Wiersze harmonogramu płatności ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Warunki płatności ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Metoda płatności odbiorcy ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Metoda płatności dostawcy ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Grupy odbiorców ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Grupy dostawców ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Grupy podatków ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Grupy podatków pozycji ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Grupy księgowania w księdze podatkowej (wersja 2) ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Jednostka kodu zwolnienia z podatku Common Data Service ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data ServiceEntity      | msdyn_taxexemptcode                        | |
| Urzędy skarbowe ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Kod podatków ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Zobacz [uwaga 1](#fin-notes). |
| Format wymiaru finansowego ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Wymiary finansowe ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Grupy potrąconych zaliczek na podatek ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Kody potrąconych zaliczek na podatek ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Plan kont ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Księga ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Zobacz [uwaga 1](#fin-notes). |
| Kategorie konta głównego ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Konto główne ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Odbiorcy wersja 3 ... kont                                                       | CustCustomerV3Entity                        | konto                                    | Zobacz [uwaga 2](#fin-notes). |
| Odbiorcy wersja 3 ... contacts                                                       | CustCustomerV3Entity                        | kontakt                                    | Zobacz [uwaga 3](#fin-notes). |
| Dostawcy wersja 2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Zobacz [uwaga 2](#fin-notes). |
| Kontakty Common Data Service wersja 2 ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | kontakt                                    | Zobacz [uwaga 4](#fin-notes). |
| Kontakty Common Data Service wersja 2 ... contacts                                    | smmContactPersonCommon Data ServiceV2Entity | kontakt                                    | Zobacz [uwaga 5](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Informacje dotyczące mapowania

1. Synchronizacja jednokierunkowa jest wykonywana z aplikacji Finance and Operations do Common Data Service.
2. Ze względu na własne zależności konieczne może być uruchomienie synchronizacji początkowej więcej niż raz. Należy pamiętać o wybraniu **Odbiorcy** jako typu relacji podczas tworzenia konta przy użyciu strony **Konta** w Common Data Service. Jeśli podczas wstępnej synchronizacji występują problemy z polem **Kontakt podstawowy**, należy usunąć to pole z mapowania, a następnie ponownie uruchomić synchronizację początkową. Po pomyślnym zakończeniu wstępnej synchronizacji zatrzymaj mapowanie i dodaj do niego pole **Podstawowy kontakt**. Następnie należy rozpocząć mapowanie, ale pominąć synchronizację początkową. Wartość pola **Kontakt podstawowy** nie zostanie uwzględniona w synchronizacji początkowej i konieczne jest ręczne migrowanie wartości.
3. Należy pamiętać o ustawieniu opcji **Możliwa sprzedaż** na wartość **Tak** na stronie **Kontakty** w Common Data Service podczas tworzenia typu **Osoby** klienta.
4. To mapowanie ma filtr na obu stronach, aby połączyć kontakty z klientami. Otwórz szczegóły mapowania, wybierz przycisk filtru (symbol lejka) obok nazwy jednostki **Sales.Contact** i upewnij się, że kryteria pliku zawierają **msdyn_contactforvendor eq true and msdyn_sellable eq false**.
5. To mapowanie ma filtr na obu stronach, aby połączyć kontakty z dostawcami. Otwórz szczegóły mapowania, wybierz przycisk filtru (symbol lejka) obok nazwy jednostki **Sales.Contact** i upewnij się, że kryteria filtru zawierają **msdyn_contactforvendor eq true and msdyn_sellable eq false**. 

## <a name="dynamics-365-human-resources-entities"></a>Jednostki usługi Dynamics 365 Human Resources

Następujące jednostki w Dynamics 365 Human Resources są wymienione w kolejności, w której należy je włączyć.

| Nazwa mapowania na stronie podwójnego zapisu | Nazwa metadanych jednostki w Human Resources | Nazwa metadanych jednostki w Common Data Service | Notatki |
|---|---|---|---|
| cdm_jobfunction — funkcja stanowiska                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes — typy zadań                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs — zadania                                               |                                   | cdm_jobs                         | |
| cdm_jobs — szczegóły zadania                                        |                                   | cdm_jobs                         | |
| cdm_positiontype — typ pozycji                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions - Bazowe stanowisko                              | HcmPositionBaseEntity             | cdm_jobposition                  | Zobacz [uwaga 1](#hr-notes). |
| cdm_jobposition - Szczegóły stanowiska                            | HcmPositionDetailEntity           | cdm_jobposition                  | Zobacz [uwaga 1](#hr-notes). |
| cdm_jobposition - Czas trwania stanowiska                           | HcmPositionDurationEntity         | cdm_jobposition                  | Zobacz [uwaga 1](#hr-notes). |
| cdm_jobposition - Hierarchie stanowisk                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Zobacz [uwaga 1](#hr-notes). |
| cdm_veteranstatus — stan kombatanta                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin - pochodzenie etniczne                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode - Kod języka                              |                                   | cdm_languagecode                 | |
| cdm_worker — pracownik                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments - Zatrudnienie                                 |                                   | cdm_employments                  | |
| cdm_employments - Szczegóły zatrudnienia                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps - Przypisania pracowników do stanowisk | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Zobacz [uwaga 2](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Informacje dotyczące mapowania

1. Jedna jednostka Common Data Service jest zamapowana na kilka jednostek aplikacji Finance and Operations.
2. To mapowanie ma odwołanie do samego siebie.

## <a name="asset-management-entities"></a>Jednostki zarządzania składnikami majątku

Poniżej znajdują się jednostki dla Zarządzania składnikami majątku dla Dynamics 365 Supply Chain Management w kolejności, w jakiej należy je włączyć.

| Nazwa mapowania na stronie podwójnego zapisu | Nazwa metadanych jednostki w Zarządzaniu składnikami majątku | Nazwa metadanych jednostki w Common Data Service | Notatki |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Stany cyklu życia składnika majątku zarządzania składnikami majątku               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Modele cyklu życia składnika majątku zarządzania składnikami majątku               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Modele cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Stany cyklu życia lokalizacji czynności konserwacyjnych zarządzania składnikami majątku | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Typy składników majątku zarządzania składnikami majątku                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Typy lokalizacji czynności konserwacyjnych zarządzania składnikami majątku            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Lokalizacje czynności konserwacyjnych zarządzania składnikami majątku                 | msdyn_functionallocations                | Zajrzyj [do notatki](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Składniki majątku zarządzania składnikami majątku                               | msdyn_customerassets                     | Zajrzyj [do notatki](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Producenci zarządzania składnikami majątku                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Modele zarządzania składnikami majątku                               | msdyn_models                             | |
| FO.AssetManagementWarranty —Common Data Service.msdyn_warranties                                                 | Gwarancja zarządzania składnikami majątku                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Informacje dotyczące mapowania

- Ze względu na własne zależności konieczne może być uruchomienie synchronizacji początkowej więcej niż raz.
