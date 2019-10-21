---
title: Ujednolicone doświadczenie korzystania z produktu
description: W tym temacie opisano integrację danych produktu między aplikacjami Finance and Operations i Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 09/3/2019
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
ms.openlocfilehash: 9dc26e0e50c0b77555d09e4a50b846c80b1d5760
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249335"
---
# <a name="unified-product-experience"></a>Ujednolicone doświadczenie korzystania z produktu

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Gdy ekosystem firmy składa się z aplikacji systemu Dynamics 365, takich jak Finance, Supply Chain Management i Sale, firma jest naturalnie skłonna używać tych aplikacji do tworzenia danych produktu źródłowego. Dzieje się tak dlatego, że te aplikacje zawierają rozbudowaną infrastrukturę produktów uzupełnioną o zaawansowane koncepcje cen oraz dokładne dane o dostępnych zapasach. Klienci korzystający z systemu zarządzania cyklem życia produktów zewnętrznych (PLM) do pozyskiwania danych produktów mogą przesyłać produkty z aplikacji Finance and Operations do innych aplikacji Dynamics 365. Ujednolicone doświadczenie korzystania z produktu w modelu danych produktów jest zintegrowane z systemem Common Data Service, dzięki czemu wszyscy użytkownicy aplikacji, w tym użytkownicy Power Platform, mogą korzystać z bogatych danych produktu pochodzących aplikacji Finance and Operations.

Oto model danych produktu z Sales.

![Model danych produktów w Sales](media/dual-write-product-4.jpg)

Oto model danych produktu z aplikacji Finance and Operations.

![Model danych dla produktów w Finance and Operations](media/dual-write-products-5.jpg)

Te dwa modele danych produktu zostały zintegrowane w Common Data Service w sposób przedstawiony poniżej.

![Model danych produktów w aplikacjach Dynamics 365](media/dual-write-products-6.jpg)

Mapowania jednostek podwójnego zapisywania dla produktów zostały zaprojektowane tak, aby dane były przesyłane tylko w czasie jak najbliższym rzeczywistemu z aplikacji Finance and Operations do Common Data Service. Jednak infrastruktura produktów została otwarta, aby była w razie potrzeby prowadzona w sposób dwukierunkowy. Klienci mogą ją dostosować na własną odpowiedzialność, ponieważ nie jest to zalecane rozwiązanie Microsoft.

## <a name="templates"></a>Szablony

Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania. W poniższej tabeli przedstawiono kolekcję mapowań jednostek, która umożliwia synchronizowanie produktów i informacji pokrewnych.

Finance and Operations | Inne aplikacje w usłudze Dynamics 365
-----------------------|--------------------------------
Zwolnione produkty (wersja 2) | msdyn\_sharedproductdetails
Odrębne produkty zwolnione w usłudze CDS | Produkt
Kod kreskowy zidentyfikowany numer produktu | msdyn\_productbarcodes
Ustawienia domyślne zamówień | msdyn\_productdefaultordersettings
Ustawienia domyślne określonego produktu (wersja 2) | msdyn_productspecificdefaultordersettings
Grupy wymiarów produktu | msdyn\_productdimensiongroups
Grupy wymiarów magazynowania | msdyn\_productstoragedimensiongroups
Grupy wymiarów śledzenia | msdyn\_producttrackingdimensiongroups
Kolory | msdyn\_productcolors
Rozmiary | msdyn\_productsizes
Style | msdyn\_productsytles
Konfiguracje | msdyn\_productconfigurations
Kolory produktu głównego | msdyn_sharedproductcolors
Rozmiary produktu głównego | msdyn_sharedproductsizes
Style produktu głównego | msdyn_sharedproductstyles
Konfiguracje produktu głównego | msdyn_sharedproductconfigurations
Wszystkie produkty | msdyn_globalproducts
Jednostka | uoms
Konwersje jednostek | msdyn_ unitofmeasureconversions
Konwersja jednostki miary określonego produktu | msdyn_productspecificunitofmeasureconversion
Oddziały | msdyn\_operationalsites
Magazyny | msdyn\_inventwarehouses

[!include [symbols](../includes/dual-write-symbols.md)]

## <a name="integration-of-products"></a>Integracja produktów

W tym modelu produkt jest reprezentowany przez kombinację dwóch encji w Common Data Service: **Produkt** i **msdyn\_sharedproductdetails**. Pierwsza encja zawiera definicję produktu (unikatowy identyfikator produktu, nazwę produktu i opis), druga encja zawiera pola przechowywane na poziomie produktu. Kombinacja tych dwóch jednostek służy do definiowania produktu zgodnie z koncepcją jednostki magazynowej (SKU). Każdy zwolniony produkt będzie miał informacje zawarte w wymienionych encjach (Szczegóły dotyczące produktu i udostępnionego produktu). Do śledzenia wszystkich produktów (zwolnionych i niezwolnionych) jest używana encja **Produkty globalne**. 

Ponieważ produkt jest reprezentowany jako jednostka SKU, pojęcia dotyczące różnych produktów, produktów głównych i wariantów produktu można przechwycić w Common Data Service w następujący sposób:

- **Produkty o podtypie produktu** to produkty, które są definiowane przez siebie Nie trzeba definiować dla nich wymiarów. Przykładem jest określona księga. W przypadku tych produktów tworzony jest jeden rekord w encji **Produktu**, a jeden rekord jest tworzony w encji **msdyn\_sharedproductdetails**. Nie utworzono rekordu rodziny produktów.
- **Produkty główne** są używane jako standardowe produkty, które posiadają definicję i reguły określające zachowanie w procesach biznesowych. Na podstawie tych definicji można generować odrębne produkty znane jako warianty produktów. Na przykład, Koszulka jest produktem głównym i może posiadać Kolor i Rozmiar jako wymiary. Można zwalniać warianty, które mają różne kombinacje tych wymiarów, np. małą, niebieską koszulkę lub średnią, zieloną koszulkę. W integracji jeden rekord na wariant jest tworzony w tabeli produktów. Ten rekord zawiera informacje specyficzne dla wariantu, takie jak różne wymiary. Informacje ogólne dotyczące produktu są przechowywane w jednostce **msdyn\_sharedproductdetails**. (Te informacje ogólne są przechowywane w danych głównych produktu.) Ponadto dla każdego produktu głównego jest tworzony jeden rekord rodziny produktów. Informacje o danych głównych produktu są synchronizowane z Common Data Service z chwilą utworzenia zwolnionego produktu głównego (ale przed zwolnieniem wariantów).
- **Odrębne produkty** odnoszą się do wszystkich produktów podtypu produktu i wszystkich wariantów produktu. 

![Model danych produktów](media/dual-write-product.png)

W przypadku włączenia funkcji podwójnego zapisywania aplikacje Finance and Operations zostaną zsynchronizowane w innych aplikacjach systemu Dynamics 365 w stanie **Wersje robocze**. Są one dodawane do pierwszej listy cen z tą samą walutą. Innymi słowy, są dodawane do pierwszej listy cen w aplikacji Dynamics 365, która odpowiada walucie firmy, w której produkt jest wydawany w aplikacji Finance and Operations. 

Aby zsynchronizować produkt z **Aktywnym** stanem, można go bezpośrednio używać w ofertach zamówień sprzedaży, na przykład należy wybrać następujące ustawienie: w obszarze **System > Administracja > Administracja systemu > Ustawienia systemu > Sprzedaż** wybierz opcję **Utwórz produkty w stanie aktywnym = tak**. 

### <a name="cds-released-distinct-products-to-product"></a>CDS zwalnia odrębne produkty do Produktu

Jednostka **Produktu** zawiera pola, które definiują produkt. Zawiera produkty indywidualne (produkty podtypu) i warianty produktu. Poniższa tabela przedstawia kolejność mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTNUMBER | >> | productnumber
PRODUCTNAME | >> | name
PRODUCTDESCRIPTION | >> | opis
ITEMNUMBER | >> | msdyn_itemnumber
CURRENCYCODE | >> | transactioncurrencyid.isocurrencycode
SALESUNITSYMBOL | >> | defaultuomid.msdyn_symbol
SALESPRICE | >> | cena
UNITCOST | >> | currentcost
PRODUCTTYPE | >> | producttypecode
SALESUNITDECIMALPRECISION | >> | quantitydecimal
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight
PRODUCTCOLORID | >> | msdyn_productcolor.msdyn_productcolorname
PRODUCTCONFIGURATIONID | >> | msdyn_productconfiguration.msdyn_productconfiguration
PRODUCTSIZEID | >> | msdyn_productsize.msdyn_productsize
PRODUCTSTYLEID | >> | msdyn_productstyle.msdyn_productstyle

### <a name="released-products-v2-to-msdyn_sharedproductdetails"></a>Zwolnione produkty V2 do msdyn\_sharedproductdetails

Jednostka **msdyn\_sharedproductdetails** zawiera pola z aplikacji Finance and Operations, które definiują produkt, i zawierają informacje finansowe i informacje dotyczące zarządzania produktem. Poniższa tabela przedstawia kolejność mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTNUMBER | > | msdyn_globalproduct.msdyn_productnumber
INTRASTATCHARGEPERCENTAGE | > | msdyn_intrastatchargepercentage
ITEMNUMBER | >> | msdyn_itemnumber
APPROXIMATESALESTAXPERCENTAGE | > | msdyn_approximatesalestaxpercentage
BESTBEFOREPERIODDAYS | > | msdyn_bestbeforeperioddays
CARRYINGCOSTABCCODE | >> | msdyn_carryingcostabccode
CONSTANTSCRAPQUANTITY | > | msdyn_constantscrapquantity
COSTCHARGESQUANTITY | > | msdyn_costchargesquantity
DEFAULTRECEIVINGQUANTITY | > | msdyn_defaultreceivingquantity
FIXEDPURCHASEPRICECHARGES | > | msdyn_fixedpurchasepricecharges
FIXEDSALESPRICECHARGES | > | msdyn_fixedsalespricecharges
GROSSDEPTH | > | msdyn_grossdepth
GROSSPRODUCTHEIGHT | > | msdyn_grossproductheight
GROSSPRODUCTWIDTH | > | msdyn_grossproductwidth
INVENTORYUNITSYMBOL | > | msdyn_inventoryunitsymbol.msdyn_symbol
ISDISCOUNTPOSREGISTRATIONPROHIBITED | >> | msdyn_isdiscountposregistrationprohibited
ISEXEMPTFROMAUTOMATICNOTIFICATIONANDCANCELLATION | >> | msdyn_exemptautomaticnotificationcancel
ISINSTALLMENTELIGIBLE | >> | msdyn_isinstallmenteligible
ISINTERCOMPANYPURCHASEUSAGEBLOCKED | >> | msdyn_isintercompanypurchaseusageblocked
ISINTERCOMPANYSALESUSAGEBLOCKED | >> | msdyn_isintercompanysalesusageblocked
ISMANUALDISCOUNTPOSREGISTRATIONPROHIBITED | >> | msdyn_ismanualdiscposregistrationprohibited
ISPHANTOM | >> | msdyn_isphantom
ISPOSREGISTRATIONBLOCKED | >> | msdyn_isposregistrationblocked
ISPOSREGISTRATIONQUANTITYNEGATIVE | >> | msdyn_isposregistrationquantitynegative
ISPURCHASEPRICEAUTOMATICALLYUPDATED | >> | msdyn_ispurchasepriceautomaticallyupdated
ISPURCHASEPRICEINCLUDINGCHARGES | >> | msdyn_ispurchasepriceincludingcharges
ISSALESWITHHOLDINGTAXCALCULATED | >> | msdyn_issaleswithholdingtaxcalculated
ISRESTRICTEDFORCOUPONS | >> | msdyn_issaleswithholdingtaxcalculated
ISSALESPRICEADJUSTMENTALLOWED | >> | msdyn_issalespriceadjustmentallowed
ISSALESPRICEINCLUDINGCHARGES | >> | msdyn_issalespriceincludingcharges
ISSCALEPRODUCT | >> | msdyn_isscaleproduct
ISSHIPALONEENABLED | >> | msdyn_isshipaloneenabled
ISUNITCOSTPRODUCTVARIANTSPECIFIC | >> | msdyn_isunitcostproductvariantspecific
ISVARIANTSHELFLABELSPRINTINGENABLED | >> | msdyn_isvariantshelflabelsprintingenabled
ISZEROPRICEPOSREGISTRATIONALLOWED | >> | msdyn_iszeropriceposregistrationallowed
KEYINPRICEREQUIREMENTSATPOSREGISTER | >> | msdyn_keyinpricerequirementsatposregister
KEYINQUANTITYREQUIREMENTSATPOSREGISTER | >> | msdyn_keyinquantityrequirementsatposregister
MARGINABCCODE | >> | msdyn_marginabccode
MAXIMUMPICKQUANTITY | > | msdyn_maximumpickquantity
MUSTKEYINCOMMENTATPOSREGISTER | >> | msdyn_mustkeyincommentatposregister
NECESSARYPRODUCTIONWORKINGTIMESCHEDULINGPROPERTYID | > | msdyn_necessaryproductionworkingtimeschedulingp
NETPRODUCTWEIGHT | > | msdyn_netproductweight
PACKINGDUTYQUANTITY | > | msdyn_packingdutyquantity
POSREGISTRATIONACTIVATIONDATE | > | msdyn_posregistrationactivationdate
POSREGISTRATIONBLOCKEDDATE | > | msdyn_posregistrationblockeddate
POSREGISTRATIONPLANNEDBLOCKEDDATE | > | msdyn_posregistrationplannedblockeddate
POTENCYBASEATTIBUTETARGETVALUE | > | msdyn_potencybaseattibutetargetvalue
POTENCYBASEATTRIBUTEVALUEENTRYEVENT | >> | msdyn_potencybaseattributevalueentryevent
PRODUCTTYPE | >> | msdyn_producttype
PRODUCTIONCONSUMPTIONDENSITYCONVERSIONFACTOR | > | msdyn_productionconsumptiondensityconversion
PRODUCTIONCONSUMPTIONDEPTHCONVERSIONFACTOR | > | msdyn_productionconsumptiondepthconversion
PRODUCTIONCONSUMPTIONHEIGHTCONVERSIONFACTOR | > | msdyn_productionconsumptionheightconversion
PRODUCTIONCONSUMPTIONWIDTHCONVERSIONFACTOR | > | msdyn_productionconsumptionwidthconversion
PRODUCTVOLUME | > | msdyn_productvolume
PURCHASECHARGESQUANTITY | > | msdyn_purchasechargesquantity
PURCHASEOVERDELIVERYPERCENTAGE | > | msdyn_purchaseoverdeliverypercentage
PURCHASEPRICE | > | msdyn_purchaseprice
PURCHASEPRICEDATE | > | msdyn_purchasepricedate
PURCHASEPRICINGPRECISION | > | msdyn_purchasepricingprecision
PURCHASEUNDERDELIVERYPERCENTAGE | > | msdyn_purchaseunderdeliverypercentage
RAWMATERIALPICKINGPRINCIPLE | >> | msdyn_rawmaterialpickingprinciple
SALESCHARGESQUANTITY | > | msdyn_saleschargesquantity
SALESOVERDELIVERYPERCENTAGE | > | msdyn_salesoverdeliverypercentage
SALESPRICE | > | msdyn_salesprice
SALESPRICECALCULATIONCHARGESPERCENTAGE | > | msdyn_salespricecalculationchargespercentage
SALESPRICECALCULATIONCONTRIBUTIONRATIO | > | msdyn_salespricecalculationcontributionratio
SALESPRICECALCULATIONMODEL | >> | msdyn_salespricecalculationmodel
SALESPRICEDATE | > | msdyn_salespricedate
SALESPRICINGPRECISION | > | msdyn_salespricingprecision
SALESUNDERDELIVERYPERCENTAGE | > | msdyn_salesunderdeliverypercentage
SALESUNITSYMBOL | > | msdyn_salesunitsymbol.msdyn_symbol
SCALEINDICATOR | >> | msdyn_scaleindicator
SELLSTARTDATE | > | msdyn_sellstartdate
SHELFADVICEPERIODDAYS | > | msdyn_shelfadviceperioddays
SHELFLIFEPERIODDAYS | > | msdyn_shelflifeperioddays
SHIPSTARTDATE | > | msdyn_shipstartdate
TAREPRODUCTWEIGHT | > | msdyn_tareproductweight
TRANSFERORDEROVERDELIVERYPERCENTAGE | > | msdyn_transferorderoverdeliverypercentage
TRANSFERORDERUNDERDELIVERYPERCENTAGE | > | msdyn_transferorderunderdeliverypercentage
UNITCOST | > | msdyn_unitcost
UNITCOSTDATE | > | msdyn_unitcostdate
UNITCOSTQUANTITY | > | msdyn_unitcostquantity
VARIABLESCRAPPERCENTAGE | > | msdyn_variablescrappercentage
WAREHOUSEMOBILEDEVICEDESCRIPTIONLINE1 | > | msdyn_warehousemobiledevicedescriptionline1
msdyn_warehousemobiledevicedescriptionline2 | > | msdyn_warehousemobiledevicedescriptionline2
WILLINVENTORYISSUEAUTOMATICALLYREPORTASFINISHED | >> | msdyn_willinventoryissueautoreportasfinished
WILLINVENTORYRECEIPTIGNOREFLUSHINGPRINCIPLE | >> | msdyn_willinventoryreceiptignoreflushing
WILLPICKINGWORKBENCHAPPLYBOXINGLOGIC | >> | msdyn_willpickingworkbenchapplyboxinglogic
WILLTOTALPURCHASEDISCOUNTCALCULATIONINCLUDEPRODUCT | >> | msdyn_willtotalpurchdiscountcalcincludeproduct
WILLTOTALSALESDISCOUNTCALCULATIONINCLUDEPRODUCT | >> | msdyn_willtotalsalesdiscountcalcincludeproduct
WILLWORKCENTERPICKINGALLOWNEGATIVEINVENTORY | >> | msdyn_willworkcenterpickingallownegativeinvent
YIELDPERCENTAGE | > | msdyn_yieldpercentage
ISUNITCOSTAUTOMATICALLYUPDATED | >> | msdyn_isunitcostautomaticallyupdated
PURCHASEUNITSYMBOL | > | msdyn_purchaseunitsymbol.msdyn_symbol
PURCHASEPRICEQUANTITY | > | msdyn_purchasepricequantity
ISUNITCOSTINCLUDINGCHARGES | >> | msdyn_isunitcostincludingcharges
FIXEDCOSTCHARGES | >> | msdyn_fixedcostcharges
MINIMUMCATCHWEIGHTQUANTITY | >> | msdyn_minimumcatchweightquantity
MAXIMUMCATCHWEIGHTQUANTITY | >> | msdyn_maximumcatchweightquantity
msdyn_maximumcatchweightquantity | >> | msdyn_alternativeitemnumber.msdyn_itemnumber
BOMUNITSYMBOL | >> | msdyn_bomunitsymbol.msdyn_symbol
CATCHWEIGHTUNITSYMBOL | >> | msdyn_catchweightunitsymbol.msdyn_symbol
COMPARISONPRICEBASEUNITSYMBOL | >> | msdyn_comparisonpricebaseunitsymbol.msdyn_symbol
PRIMARYVENDORACCOUNTNUMBER | >> | msdyn_vendorid.msdyn_vendoraccountnumber
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight
PRODUCTDIMENSIONGROUPNAME | >> | msdyn_productdimensiongroupid.msdyn_groupname

## <a name="all-product-to-msdyn_global-products"></a>Cały produkt do produktów msdyn_global

Jednostka wszystkie produkty zawiera wszystkie produkty dostępne w aplikacjach Finanse, w tym produkty zwolnione oraz produkty niezwolnione. Te produkty są dostępne w Common Data Service przy użyciu następujących mapowań:

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTNAME | >> | msdyn_productname
PRODUCTNUMBER | >> | msdyn_productnumber

## <a name="product-dimensions"></a>Wymiary produktu 

Wymiary produktu to cechy, które określają wariant produktu. Cztery wymiary produktu (kolor, rozmiar, styl i konfiguracja) są również mapowane w Common Data Service w celu zdefiniowania wariantów produktu. Na poniższej ilustracji przedstawiono model danych dla wymiaru produktu Kolor. Ten sam model jest stosowany do rozmiarów, stylów i konfiguracji. 

![Model danych produktów](media/dual-write-product-2.PNG)

### <a name="colors"></a>Kolory

Dostępne są następujące kolory w Common Data Service w ramach następujących mapowań:

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
COLORID | \>\> | msdyn\_productcolorname

### <a name="sizes"></a>Rozmiary

Dostępne są następujące rozmiary w Common Data Service w ramach następujących mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
SIZEID | \>\> | msdyn\_productsize

### <a name="styles"></a>Style

Dostępne są następujące style w Common Data Service w ramach następujących mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
STYLEID | \>\> | msdyn\_productstyle

### <a name="configurations"></a>Konfiguracje

Dostępne są następujące konfiguracje w Common Data Service w ramach następujących mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CONFIGURATIONID | \>\> | msdyn\_name

Jeśli produkt ma różne wymiary produktu (np. produkt główny ma rozmiar i kolor jako wymiary produktu), każdy odrębny produkt (każdy wariant produktu) jest definiowany jako kombinacja tych wymiarów produktu. Na przykład numer produktu B0001 to bardzo mała czarna koszulka, a numer produktu B0002 jest małą czarną koszulką. W takim przypadku definiowane są istniejące kombinacje wymiarów produktu. Na przykład koszulka z powyższego przykładu może być bardzo mała i czarna, mała i czarna, średnia i czarna, lub duża i czarna, ale nie może być bardzo duża i czarna. Innymi słowy, wymiary produktów, które może pobrać produkt główny produktu, są określone, a warianty mogą być zwalniane na podstawie tych wartości.

Aby śledzić wymiary produktu, które może przyjąć produkt główny, w Common Data Service dla każdego wymiaru produktu są tworzone i mapowane następujące jednostki. Aby uzyskać więcej informacji, zobacz [Omówienie informacji o produktach](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

### <a name="shared-product-color"></a>Udostępniony kolor produktu

Jednostka **Udostepniony kolor produktu** wskazuje kolory, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych. Poniższa tabela przedstawia kolejność mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTCOLORID | \>\> | msdyn\_productcolorid.msdyn\_productcolorname
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid. msdyn\_Itemnumber
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_retaildisplayorder

### <a name="shared-product-size"></a>Udostępniony rozmiar produktu

Jednostka **Udostepniony rozmiar produktu** wskazuje rozmiary, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych. Poniższa tabela przedstawia kolejność mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid. msdyn\_Itemnumber
PRODUCTSIZEID | \>\> | msdyn\_productsizeid.msdyn\_productsize
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

### <a name="shared-product-style"></a>Udostępnione style produktu

Jednostka **Udostepnione style produktu** wskazuje style, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych. Poniższa tabela przedstawia kolejność mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailsid.msdyn\_itemnumber
PRODUCTSTYLEID | \>\> | msdyn\_productstyleintegration
PRODUCTSTYLEID | \>\> | msdyn\_productstyleid.msdyn\_productstyle
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

### <a name="shared-product-configuration"></a>Udostepnione konfiguracje produktu

Jednostka **Udostepnione konfiguracje produktu** wskazuje konfiguracje, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych. Poniższa tabela przedstawia kolejność mapowań.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
CONTAINERUNITSYMBOL | \>\> | msdyn\_containerunitsymbol
PRODUCTCONFIGURATIONID | \>\> | msdyn\_productconfigurationid.msdyn\_productconfiguration
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid. msdyn\_Itemnumber
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

## <a name="product-number-identifier-bar-codes"></a>Kod kreskowy identyfikujący numer produktu

Kody kreskowe produktów służą do jednoznacznego identyfikowania produktów. Te produkty są dostępne w Common Data Service przy użyciu następujących mapowań używanych do tworzenia kodów kreskowych produktów:

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
PRODUCTNUMBER | \> | msdyn\_productnumberid.productnumber
BARCODE | \> | msdyn\_name
BARCODE | \> | msdyn\_barcode
PRODUCTQUANTITY | \> | msdyn\_productquantity
PRODUCTDESCRIPTION | \> | msdyn\_productdescription
BARCODESETUPID | \> | msdyn\_barcodesetupid
PRODUCTQUANTITYUNITSYMBOL | \> | msdyn\_unitofmeasureid.name
ISDEFAULTSCANNEDBARCODE | \>\> | msdyn\_isdefaultscannedbarcode
ISDEFAULTPRINTEDBARCODE | \>\> | msdyn\_isdefaultprintedbarcode
ISDEFAULTDISPLAYEDBARCODE | \>\> | msdyn\_isdefaultdisplayedbarcode

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Domyślne ustawienia zamówień i domyślne ustawienia zamówień charakterystycznych dla produktu

Domyślne ustawienia zamówień definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień. Te informacje będą dostępne w CDS przy użyciu jednostki domyślne ustawienia zamówienia oraz domyślny stan produktu. Możesz przeczytać więcej informacji o funkcjach na [Ustawienia domyślne zamówień](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/production-control/default-order-settings).

### <a name="default-order-settings"></a>Ustawienia domyślne zamówień

Następujące mapowania są używane jako domyślne ustawienia zamówienia dostępne w Common Data Service.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
INVENTWAREHOUSEID | = | msdyn_inventorywarehouse.msdyn_warehouseidentifier
INVENTORYSITEID | = | msdyn_inventorysite.msdyn_siteid
INVENTORYATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_inventoryatpdelayeddemandoffsetdays
INVENTORYATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_inventoryatpdelayedsupplyoffsetdays
ITEMNUMBER | = | msdyn_itemnumber.msdyn_itemnumber
INVENTORYATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_inventoryatpbackwarddemandtimefencedays
INVENTORYATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_inventoryatpbackwardsupplytimefencedays
INVENTORYATPTIMEFENCEDAYS | = | msdyn_inventoryatptimefencedays
MAXIMUMINVENTORYORDERQUANTITY | = | msdyn_maximuminventoryorderquantity
MAXIMUMPROCUREMENTORDERQUANTITY | = | msdyn_maximumprocurementorderquantity
MAXIMUMSALESORDERQUANTITY | = | msdyn_maximumsalesorderquantity
MINIMUMINVENTORYORDERQUANTITY | = | msdyn_minimuminventoryorderquantity
MINIMUMPROCUREMENTORDERQUANTITY | = | msdyn_minimumprocurementorderquantity
MINIMUMSALESORDERQUANTITY | = | msdyn_minimumsalesorderquantity
STANDARDINVENTORYORDERQUANTITY | = | msdyn_standardinventoryorderquantity
STANDARDPROCUREMENTORDERQUANTITY | = | msdyn_standardprocurementorderquantity
STANDARDSALESORDERQUANTITY | = | msdyn_standardsalesorderquantity
INVENTORYLEADTIMEDAYS | = | msdyn_inventoryleadtimedays
INVENTORYQUANTITYMULTIPLES | = | msdyn_inventoryquantitymultiples
PROCUREMENTQUANTITYMULTIPLES | = | msdyn_procurementquantitymultiples
SALESQUANTITYMULTIPLES | = | msdyn_salesquantitymultiples
PROCUREMENTSITEID | = | msdyn_procurementsite.msdyn_siteid
PROCUREMENTLEADTIMEDAYS | = | msdyn_procurementleadtimedays
SALESSITEID | = | msdyn_salessite.msdyn_siteid
SALESATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_salesatpdelayeddemandoffsetdays
SALESATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_salesatpdelayedsupplyoffsetdays
SALESATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_salesatpbackwarddemandtimefencedays
SALESATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_salesatpbackwardsupplytimefencedays
SALESATPTIMEFENCEDAYS | = | msdyn_salesatptimefencedays
SALESLEADTIMEDAYS | = | msdyn_salesleadtimedays
PROCUREMENTWAREHOUSEID | = | msdyn_procurementwarehouse.msdyn_warehouseidentifier
SALESWAREHOUSEID | = | msdyn_saleswarehouse.msdyn_warehouseidentifier
AREINVENTORYORDERPROMISINGDEFAULTSOVERRIDDEN | >< | msdyn_areinventoryorderdefaultsoverridden
INVENTORYORDERPROMISINGMETHOD | >< | msdyn_inventoryorderpromisingmethod
ISINVENTORYATPINCLUDINGPLANNEDORDERS | >< | msdyn_isinventoryatpincludingplannedorders
ISINVENTORYUSINGWORKINGDAYS | >< | msdyn_isinventoryusingworkingdays
ISINVENTORYSITEMANDATORY | >< | msdyn_isinventorysitemandatory
ISINVENTORYPROCESSINGSTOPPED | >< | msdyn_isinventoryprocessingstopped
ISPROCUREMENTUSINGWORKINGDAYS | >< | msdyn_isprocurementusingworkingdays
ISPROCUREMENTSITEMANDATORY | >< | msdyn_isprocurementsitemandatory
ISPROCUREMENTPROCESSINGSTOPPED | >< | msdyn_isprocurementprocessingstopped
ARESALESORDERPROMISINGDEFAULTSOVERRIDDEN | >< | msdyn_aresalesorderdefaultsoverridden
SALESORDERPROMISINGMETHOD | >< | msdyn_salesorderpromisingmethod
ISSALESATPINCLUDINGPLANNEDORDERS | >< | msdyn_issalesatpincludingplannedorders
ISSALESSITEMANDATORY | >< | msdyn_issalessitemandatory
ISSALESLEADTIMEOVERRIDDEN | >< | msdyn_issalesleadtimeoverridden
ISSALESPROCESSINGSTOPPED | >< | msdyn_issalesprocessingstopped
ISINVENTORYWAREHOUSEMANDATORY | >< | msdyn_isinventorywarehousemandatory
ISPROCUREMENTWAREHOUSEMANDATORY | >< | msdyn_isprocurementwarehousemandatory
ISSALESWAREHOUSEMANDATORY | >< | msdyn_issaleswarehousemandatory

### <a name="product-specific-default-order-settings"></a>Ustawienia domyślne określonego produktu (wersja 2)

Następujące mapowania są używane jako domyślne ustawienia określonych produktów dostępne w Common Data Service.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
INVENTORYWAREHOUSEID | = | msdyn_inventorywarehouse.msdyn_warehouseidentifier
INVENTORYSITEID | = | msdyn_inventorysite.msdyn_siteid
INVENTORYATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_inventoryatpdelayeddemandoffsetdays
INVENTORYATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_inventoryatpdelayedsupplyoffsetdays
ITEMNUMBER | = | msdyn_itemnumber.msdyn_itemnumber
INVENTORYATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_inventoryatpbackwarddemandtimefencedays
INVENTORYATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_inventoryatpbackwardsupplytimefencedays
INVENTORYATPTIMEFENCEDAYS | = | msdyn_inventoryatptimefencedays
MAXIMUMINVENTORYORDERQUANTITY | = | msdyn_maximuminventoryorderquantity
MAXIMUMPROCUREMENTORDERQUANTITY | = | msdyn_maximumprocurementorderquantity
MAXIMUMSALESORDERQUANTITY | = | msdyn_maximumsalesorderquantity
MINIMUMINVENTORYORDERQUANTITY | = | msdyn_minimuminventoryorderquantity
MINIMUMPROCUREMENTORDERQUANTITY | = | msdyn_minimumprocurementorderquantity
MINIMUMSALESORDERQUANTITY | = | msdyn_minimumsalesorderquantity
STANDARDINVENTORYORDERQUANTITY | = | msdyn_standardinventoryorderquantity
STANDARDPROCUREMENTORDERQUANTITY | = | msdyn_standardprocurementorderquantity
STANDARDSALESORDERQUANTITY | = | msdyn_standardsalesorderquantity
INVENTORYLEADTIMEDAYS | = | msdyn_inventoryleadtimedays
INVENTORYQUANTITYMULTIPLES | = | msdyn_inventoryquantitymultiples
PROCUREMENTQUANTITYMULTIPLES | = | msdyn_procurementquantitymultiples
SALESQUANTITYMULTIPLES | = | msdyn_salesquantitymultiples
PROCUREMENTSITEID | = | msdyn_procurementsite.msdyn_siteid
PROCUREMENTLEADTIMEDAYS | = | msdyn_procurementleadtimedays
SALESSITEID | = | msdyn_salessite.msdyn_siteid
SALESATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_salesatpdelayeddemandoffsetdays
SALESATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_salesatpdelayedsupplyoffsetdays
SALESATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_salesatpbackwarddemandtimefencedays
SALESATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_salesatpbackwardsupplytimefencedays
SALESATPTIMEFENCEDAYS | = | msdyn_salesatptimefencedays
SALESLEADTIMEDAYS | = | msdyn_salesleadtimedays
PROCUREMENTWAREHOUSEID | = | msdyn_procurementwarehouse.msdyn_warehouseidentifier
SALESWAREHOUSEID | = | msdyn_saleswarehouse.msdyn_warehouseidentifier
AREINVENTORYDEFAULTORDERSETTINGSOVERRIDDEN | >< | msdyn_areinventoryorderdefaultsoverridden
INVENTORYORDERPROMISINGMETHOD | >< | msdyn_inventoryorderpromisingmethod
ISINVENTORYATPINCLUDINGPLANNEDORDERS | >< | msdyn_isinventoryatpincludingplannedorders
ISINVENTORYUSINGWORKINGDAYS | >< | msdyn_isinventoryusingworkingdays
ISINVENTORYSITEMANDATORY | >< | msdyn_isinventorysitemandatory
ISINVENTORYPROCESSINGSTOPPED | >< | msdyn_isinventoryprocessingstopped
ISPROCUREMENTUSINGWORKINGDAYS | >< | msdyn_isprocurementusingworkingdays
ISPROCUREMENTSITEMANDATORY | >< | msdyn_isprocurementsitemandatory
ISPROCUREMENTPROCESSINGSTOPPED | >< | msdyn_isprocurementprocessingstopped
ARESALESDEFAULTORDERSETTINGSOVERRIDDEN | >< | msdyn_aresalesorderdefaultsoverridden
SALESORDERPROMISINGMETHOD | >< | msdyn_salesorderpromisingmethod
ISSALESATPINCLUDINGPLANNEDORDERS | >< | msdyn_issalesatpincludingplannedorders
ISSALESSITEMANDATORY | >< | msdyn_issalessitemandatory
ISSALESLEADTIMEOVERRIDDEN | >< | msdyn_issalesleadtimeoverridden
ISSALESPROCESSINGSTOPPED | >< | msdyn_issalesprocessingstopped
ISINVENTORYWAREHOUSEMANDATORY | >< | msdyn_isinventorywarehousemandatory
ISPROCUREMENTWAREHOUSEMANDATORY | >< | msdyn_isprocurementwarehousemandatory
ISSALESWAREHOUSEMANDATORY | >< | msdyn_issaleswarehousemandatory
OPERATIONALSITEID | = | msdyn_operationalsite.msdyn_siteid
PRODUCTCOLORID | = | msdyn_productcolor.msdyn_productcolorname
PRODUCTCONFIGURATIONID | = | msdyn_productconfiguration.msdyn_productconfiguration
PRODUCTSIZEID | = | msdyn_productsize.msdyn_productsize
PRODUCTSTYLEID | = | msdyn_productstyle.msdyn_productstyle

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Jednostka miary i konwersje jednostki miary

Jednostki miary i odpowiednie konwersje będą dostępne w Common Data Service w następującym modelu danych widocznym na diagramie.

![Model danych produktów](media/dual-write-product-3.PNG)

Pojęcie jednostka miary jest zintegrowane między aplikacjami Finance and Operation, a innymi aplikacjami Dynamics 365. Dla każdej klasy jednostek w aplikacji Finance and Operations jest tworzona grupa jednostek w aplikacji Dynamics 365, która zawiera jednostki należące do klasy jednostek. Domyślna jednostka podstawowa jest również tworzona dla każdej grupy jednostek. 

### <a name="unit-of-measure"></a>Jednostka miary

Poniższe mapowania służą do tworzenia jednostek miary w aplikacjach Finance and Operations dostępnych w module Common Data Service.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
UNITSYMBOL | >> | msdyn_symbol
UNITCLASS | >> | msdyn_externalunitclassname
DECIMALPRECISION | >> | msdyn_decimalprecision
ISBASEUNIT | >> | msdyn_isbaseunit
ISSYSTEMUNIT | >> | msdyn_issystemunit
SYSTEMOFUNITS | >> | msdyn_systemofunits
UNITSYMBOL | >> | name
UNITDESCRIPTION | >> | msdyn_description

### <a name="unit-of-measure-conversions"></a>Konwersja jednostek miar

Poniższe mapowania służą do tworzenia konwersji jednostek miary w aplikacjach Finance and Operations dostępnych w module Common Data Service.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
DENOMINATOR | = | msdyn_denominator
NUMERATOR | = | msdyn_numerator
FACTOR | = | msdyn_factor
INNEROFFSET | = | msdyn_inneroffset
OUTEROFFSET | = | msdyn_outeroffset
ROUNDING | >< | msdyn_rounding
TOUNITSYMBOL | = | msdyn_tounit.msdyn_symbol
FROMUNITSYMBOL | = | msdyn_fromunit.msdyn_symbol

### <a name="product-specific-unit-of-measure-conversions"></a>Konwersja jednostki miary określonego produktu

Poniższe mapowania służą do tworzenia konwersji jednostek miary określonych produktów w aplikacjach Finance and Operations dostępnych w module Common Data Service.

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
DENOMINATOR | = | msdyn_denominator
NUMERATOR | = | msdyn_numerator
FACTOR | = | msdyn_factor
FROMUNITSYMBOL | = | msdyn_fromunit.msdyn_symbol
TOUNITSYMBOL | = | msdyn_tounit.msdyn_symbol
PRODUCTNUMBER | = | msdyn_globalproduct.msdyn_productnumber
INNEROFFSET | = | msdyn_inneroffset
OUTEROFFSET | = | msdyn_outeroffset
ROUNDING | >< | msdyn_rounding

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Zasady dotyczące produktu: Grupa wymiarów, śledzenie i magazynowanie

Zasady dotyczące produktów to zestawy zasad używanych do definiowania produktów i ich charakterystyki w magazynie. Grupę wymiarów produktu, Grupę wymiarów śledzenia produktu i grupę wymiarów magazynowania można odnaleźć jako zasady produktu. 

### <a name="product-dimension-group"></a>Grupa wymiarów produktu

Grupa wymiarów produktu określa, które wymiary produktu definiują produkt. Dostępne są następujące wymiary produktu: rozmiar, kolor, styl i konfiguracja. Grupy wymiarów produktów są dostępne w Common Data Service przy użyciu następujących mapowań. 

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
WILLSALESPRICESEARCHUSEPRODUCTSTYLE | >< | msdyn_willsalespricesearchuseproductstyle
WILLPURCHASEPRICESEARCHUSEPRODUCTSIZE | >< | msdyn_willpurchasepricesearchuseproductsize
WILLSALESPRICESEARCHUSEPRODUCTCONFIGURATION | >< | msdyn_willsalespricesearchuseprodconfig
WILLSALESPRICESEARCHUSEPRODUCTCOLOR | >< | msdyn_willsalespricesearchuseproductcolor
WILLPURCHASEPRICESEARCHUSEPRODUCTSTYLE | >< | msdyn_willpurchasepricesearchuseproductstyle
WILLPURCHASEPRICESEARCHUSEPRODUCTCONFIGURATION | >< | msdyn_willpurchpricesearchuseprodconfig
WILLPURCHASEPRICESEARCHUSEPRODUCTCOLOR | >< | msdyn_willpurchpricesearchuseproductcolor
ISPRODUCTSTYLEACTIVE | >< | msdyn_isproductstyleactive
ISPRODUCTSIZEACTIVE | >< | msdyn_isproductsizeactive
ISPRODUCTCONFIGURATIONACTIVE | >< | msdyn_isproductconfigurationactive
ISPRODUCTCOLORACTIVE | >< | msdyn_isproductcoloractive
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
PRODUCTVARIANTNOMENCLATURENAME | = | msdyn_productvariantnomenclaturename
WILLSALESPRICESEARCHUSEPRODUCTSIZE | >< | msdyn_willsalespricesearchuseproductsize

### <a name="product-tracking-dimension-group"></a>Grupy wymiarów śledzenia produktu

Grupa wymiarów śledzenia produktu reprezentuje metodę używaną do śledzenia produktu w magazynie. Są dostępne w Common Data Service przy użyciu następujących mapowań. 

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
SERIALNUMBERCAPTURINGOPERATION | >< | msdyn_serialnumbercapturingoperation
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
ISSERIALNUMBERENABLEDFORPRODUCTIONCONSUMPTIONPROCESS | >< | msdyn_issnenabledforpcprocess
ISSERIALNUMBERCONTROLENABLED | >< | msdyn_isserialnumbercontrolenabled
ISSERIALNUMBERENABLEDFORSALESPROCESS | >< | msdyn_isserialnumberenabledforsalesprocess
ISSERIALNUMBERACTIVE | >< | msdyn_isserialnumberactive
ISSALESPRICEBYSERIALNUMBER | >< | msdyn_issalespricebyserialnumber
ISSALESPRICEBYBATCHNUMBER | >< | msdyn_issalespricebybatchnumber
ISPURCHASEPRICEBYSERIALNUMBER | >< | msdyn_ispurchasepricebyserialnumber
ISPURCHASEPRICEBYBATCHNUMBER | >< | msdyn_ispurchasepricebybatchnumber
ISPRIMARYSTOCKINGENABLEDFORSERIALNUMBER | >< | msdyn_isprimarystockingenabledforsn
ISPRIMARYSTOCKINGENABLEDFORBATCHNUMBER | >< | msdyn_isprimarystockingenabledforbn
ISPHYSICALINVENTORYENABLEDFORSERIALNUMBER | >< | msdyn_isphysicalinventoryenabledforsn
ISPHYSICALINVENTORYENABLEDFORBATCHNUMBER | >< | msdyn_isphysicalinventoryenabledforbn
ISFINANCIALINVENTORYENABLEDFORSERIALNUMBER | >< | msdyn_isfinancialinventoryenabledforsn
ISFINANCIALINVENTORYENABLEDFORBATCHNUMBER | >< | msdyn_isfinancialinventoryenabledforbn
ISCOVERAGEPLANENABLEDFORSERIALNUMBER | >< | msdyn_iscoverageplanenabledforserialnumber
ISCOVERAGEPLANENABLEDFORBATCHNUMBER | >< | msdyn_iscoverageplanenabledforbatchnumber
ISBLANKRECEIPTALLOWEDFORSERIALNUMBER | >< | msdyn_isblankreceiptallowedforserialnumber
ISBLANKRECEIPTALLOWEDFORBATCHNUMBER | >< | msdyn_isblankreceiptallowedforbatchnumber
ISBLANKISSUEALLOWEDFORSERIALNUMBER | >< | msdyn_isblankissueallowedforserialnumber
ISBLANKISSUEALLOWEDFORBATCHNUMBER | >< | msdyn_isblankissueallowedforbatchnumber
ISBATCHNUMBERACTIVE | >< | msdyn_isbatchnumberactive
ISINVENTORYOWNERACTIVE | >< | msdyn_isinventoryowneractive

### <a name="product-storage-dimension-group"></a>Grupy wymiarów magazynowania produktu

Grupa wymiarów magazynowania produktu reprezentuje metodę używaną do definiowania rozmieszczenia produktu w magazynie. Są dostępne w Common Data Service przy użyciu następujących mapowań. 

Pole źródłowe | Typ mapy | Pole docelowe
---|---|---
WILLSALESPRICESEARCHUSEWAREHOUSE | >< | msdyn_willsalespricesearchusewarehouse
WILLSALESPRICESEARCHUSESITE | >< | msdyn_willsalespricesearchusesite
WILLSALESPRICESEARCHUSEINVENTORYSTATUS | >< | msdyn_willsalespricesearchuseinventorystatus
WILLPURCHASEPRICESEARCHUSEWAREHOUSE | >< | msdyn_willpurchasepricesearchusewarehouse
WILLPURCHASEPRICESEARCHUSESITE | >< | msdyn_willpurchasepricesearchusesite
WILLPURCHASEPRICESEARCHUSEINVENTORYSTATUS | >< | msdyn_willpurchpricesearchuseinventstatus
WILLCOVERAGEPLANNINGUSEWAREHOUSE | >< | msdyn_willcoverageplanusewarehouse
WILLCOVERAGEPLANNINGUSELOCATION | >< | msdyn_iscoverageplanenabledforlocation
WILLCOVERAGEPLANNINGUSEINVENTORYSTATUS | >< | msdyn_willcoverageplanuseinventorystatus
AREADVANCEDWAREHOUSEMANAGEMENTPROCESSESENABLED | >< | msdyn_areadvancedwmprocessesenabled
ISWAREHOUSEPRIMARYSTORAGEDIMENSION | >< | msdyn_iswarehouseprimarystoragedimension
ISWAREHOUSEMANDATORY | >< | msdyn_iswarehousemandatory
ISPHYSICALINVENTORYENABLEDFORWAREHOUSE | >< | msdyn_isphysicalinventoryenabledforwarehouse
ISPHYSICALINVENTORYENABLEDFORLOCATION | >< | msdyn_isphysicalinventoryenabledforlocation
ISLOCATIONACTIVE | >< | msdyn_islocationactive
ISFINANCIALINVENTORYENABLEDFORWAREHOUSE | >< | msdyn_isfinancialinventoryenabledforwarehouse
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
ISBLANKRECEIPTALLOWEDFORLOCATION | >< | msdyn_isblankreceiptallowedforlocation
ISBLANKISSUEALLOWEDFORLOCATION | >< | msdyn_isblankissueallowedforlocation

