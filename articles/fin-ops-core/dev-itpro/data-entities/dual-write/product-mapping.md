---
title: Ujednolicone doświadczenie korzystania z produktu
description: W tym temacie opisano integrację danych produktu między aplikacjami Finance and Operations i Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 12/12/2019
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
ms.openlocfilehash: 3b9a1485d37da614eea2427735e0e1323897682d
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621335"
---
# <a name="unified-product-experience"></a>Ujednolicone działanie produktu

[!include [banner](../../includes/banner.md)]



Gdy ekosystem firmy składa się z aplikacji systemu Dynamics 365, takich jak Finance, Supply Chain Management i Sale, firmy często używają tych aplikacji do tworzenia danych produktu źródłowego. Dzieje się tak dlatego, że te aplikacje zawierają rozbudowaną infrastrukturę produktów uzupełnioną o zaawansowane koncepcje cen oraz dokładne dane o dostępnych zapasach. Firmy korzystające z systemu Product Lifecycle Management (PLM) do pozyskiwania danych produktów mogą przesyłać produkty z aplikacji Finance and Operations do innych aplikacji Dynamics 365. Ujednolicone doświadczenie korzystania z produktu w modelu danych produktów jest zintegrowane z Common Data Service, dzięki czemu wszyscy użytkownicy aplikacji, w tym użytkownicy Power Platform, mogą korzystać z bogatych danych produktu pochodzących aplikacji Finance and Operations.

Oto model danych produktu z Sales.

![Model danych produktów w CE](media/dual-write-product-4.jpg)

Oto model danych produktu z aplikacji Finance and Operations.

![Model danych produktów w Finance and Operations](media/dual-write-products-5.jpg)

Te dwa modele danych produktu zostały zintegrowane w Common Data Service w sposób przedstawiony poniżej.

![Model danych produktów w aplikacjach Dynamics 365](media/dual-write-products-6.jpg)

Mapowania jednostek podwójnego zapisywania dla produktów zostały zaprojektowane tak, aby dane były przesyłane tylko w czasie jak najbliższym rzeczywistemu z aplikacji Finance and Operations do Common Data Service. Jednak infrastruktura produktów została otwarta, aby była w razie potrzeby prowadzona w sposób dwukierunkowy. Mimo że można ją dostosować na własną odpowiedzialność, ponieważ nie jest to zalecane rozwiązanie Microsoft.

## <a name="templates"></a>Szablony

Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania. W poniższej tabeli przedstawiono kolekcję mapowań jednostek, która umożliwia synchronizowanie produktów i informacji pokrewnych.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | opis
-----------------------|--------------------------------|---
Zwolnione produkty (wersja 2) | msdyn\_sharedproductdetails | Jednostka **msdyn\_sharedproductdetails** zawiera pola z aplikacji Finance and Operations, które definiują produkt, i zawierają informacje finansowe i informacje dotyczące zarządzania produktem. 
Common Data Service odrębne produkty zwolnione w usłudze CDS | Produkt | Jednostka **Produktu** zawiera pola, które definiują produkt. Zawiera produkty indywidualne (produkty podtypu) i warianty produktu. Poniższa tabela przedstawia kolejność mapowań.
Kod kreskowy zidentyfikowany numer produktu | msdyn\_productbarcodes | Kody kreskowe produktów służą do jednoznacznego identyfikowania produktów.
Ustawienia domyślne zamówień | msdyn\_productdefaultordersettings
Ustawienia domyślne określonego produktu (wersja 2) | msdyn_productdefaultordersettings
Grupy wymiarów produktu | msdyn\_productdimensiongroups | Grupa wymiarów produktu określa, które wymiary produktu definiują produkt. 
Grupy wymiarów magazynowania | msdyn\_productstoragedimensiongroups | Grupa wymiarów magazynowania produktu reprezentuje metodę używaną do definiowania rozmieszczenia produktu w magazynie.
Grupy wymiarów śledzenia | msdyn\_producttrackingdimensiongroups | Grupa wymiarów śledzenia produktu reprezentuje metodę używaną do śledzenia produktu w magazynie.
Kolory | msdyn\_productcolors
Rozmiary | msdyn\_productsizes
Style | msdyn\_productsytles
Konfiguracje | msdyn\_productconfigurations
Kolory produktu głównego | msdyn_sharedproductcolors | Jednostka **Udostepniony kolor produktu** wskazuje kolory, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych.
Rozmiary produktu głównego | msdyn_sharedproductsizes | Jednostka **Udostępnij rozmiar produktu** wskazuje rozmiary, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych.
Style produktu głównego | msdyn_sharedproductstyles | Jednostka **Udostepnione style produktu** wskazuje style, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych.
Konfiguracje produktu głównego | msdyn_sharedproductconfigurations | Jednostka **Udostepnione konfiguracje produktu** wskazuje konfiguracje, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Common Data Service w celu zachowania spójności danych.
Wszystkie produkty | msdyn_globalproducts | Jednostka wszystkie produkty zawiera wszystkie produkty dostępne w aplikacjach Finance and Operations, w tym produkty zwolnione oraz produkty niezwolnione.
Jednostka | uoms
Konwersje jednostek | msdyn_ unitofmeasureconversions
Konwersja jednostki miary określonego produktu | msdyn_productspecificunitofmeasureconversion
Kategorie produktów | msdyn_productcategories | Każda kategoria produktu oraz informacje o jego strukturze i charakterystyce znajdują się w jednostce kategorii produktów. 
Hierarchie kategorii produktów | msdyn_productcategoryhierarhies | Hierarchie produktów umożliwiają łączenie produktów w kategorie i grupy. Hierarchie kategorii są dostępne w Common Data Service przy użyciu jednostki Hierarchia kategorii produktów. 
Role hierarchii kategorii produktów | msdyn_productcategoryhierarchies | Hierarchie produktów mogą być używane w różnych rolach w D365 Finance and Operations. Określają, która kategoria ma być używana w każdej roli, w której jest używana jednostka roli Kategoria produktu. 
Przypisania kategorii produktów | msdyn_productcategoryassignments | Aby przypisać produkt do kategorii, można użyć jednostki przypisań kategorii produktów.

## <a name="integration-of-products"></a>Integracja produktów

W tym modelu produkt jest reprezentowany przez kombinację dwóch encji w Common Data Service: **Produkt** i **msdyn\_sharedproductdetails**. Pierwsza encja zawiera definicję produktu (unikatowy identyfikator produktu, nazwę produktu i opis), druga encja zawiera pola przechowywane na poziomie produktu. Kombinacja tych dwóch jednostek służy do definiowania produktu zgodnie z koncepcją jednostki magazynowej (SKU). Każdy zwolniony produkt będzie miał informacje zawarte w wymienionych encjach (Szczegóły dotyczące produktu i udostępnionego produktu). Do śledzenia wszystkich produktów (zwolnionych i niezwolnionych) jest używana encja **Produkty globalne**. 

Ponieważ produkt jest reprezentowany jako jednostka SKU, pojęcia dotyczące różnych produktów, produktów głównych i wariantów produktu można przechwycić w Common Data Service w następujący sposób:

- **Produkty o podtypie produktu** to produkty, które są definiowane przez siebie Nie trzeba definiować wymiarów. Przykładem jest określona księga. W przypadku tych produktów tworzony jest jeden rekord w encji **Produktu**, a jeden rekord jest tworzony w encji **msdyn\_sharedproductdetails**. Nie utworzono rekordu rodziny produktów.
- **Produkty główne** są używane jako standardowe produkty, które posiadają definicję i reguły określające zachowanie w procesach biznesowych. Na podstawie tych definicji można generować odrębne produkty znane jako warianty produktów. Na przykład, Koszulka jest produktem głównym i może posiadać Kolor i Rozmiar jako wymiary. Można zwalniać warianty, które mają różne kombinacje tych wymiarów, np. małą, niebieską koszulkę lub średnią, zieloną koszulkę. W integracji jeden rekord na wariant jest tworzony w tabeli produktów. Ten rekord zawiera informacje specyficzne dla wariantu, takie jak różne wymiary. Informacje ogólne dotyczące produktu są przechowywane w jednostce **msdyn\_sharedproductdetails**. (Te ogólne informacje są przechowywane w produkcie głównym). Informacje o danych głównych produktu są synchronizowane z Common Data Service z chwilą utworzenia zwolnionego produktu głównego (ale przed zwolnieniem wariantów).
- **Odrębne produkty** odnoszą się do wszystkich produktów podtypu produktu i wszystkich wariantów produktu. 

![Model danych produktów](media/dual-write-product.png)

W przypadku włączenia funkcji podwójnego zapisywania aplikacje z Finance and Operations zostaną zsynchronizowane w innych aplikacjach Dynamics 365 w stanie **Wersje robocze**. Są one dodawane do pierwszej listy cen z tą samą walutą. Innymi słowy, są dodawane do pierwszej listy cen w aplikacji Dynamics 365, która odpowiada walucie firmy, w której produkt jest wydawany w aplikacji Finance and Operations. 

Produkty domyślne z Finance and Operations operacyjnych są synchronizowane z innymi aplikacjami systemu Dynamics 365 w stanie **wersja robocza**. Aby zsynchronizować produkt z **Aktywnym** stanem, można go bezpośrednio używać w ofertach zamówień sprzedaży, na przykład należy wybrać następujące ustawienie: w obszarze **System > Administracja > Administracja systemu > Ustawienia systemu > karta Sprzedaż** wybierz opcję **Utwórz produkty w stanie aktywnym = tak**. 

Zauważ, że synchronizacja produktów jest spowodowana przez Finance and Operations do Common Data Service. Oznacza to, że wartości pól jednostki produktu mogą być zmieniane w Common Data Service, ale po wyzwoleniu synchronizacji (po zmodyfikowaniu pola produktu w module w aplikacji Finance and Operations) zostaną one zastąpione wartościami w Common Data Service. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Wymiary produktu 

Wymiary produktu to cechy, które określają wariant produktu. Cztery wymiary produktu (kolor, rozmiar, styl i konfiguracja) są również mapowane w Common Data Service w celu zdefiniowania wariantów produktu. Na poniższej ilustracji przedstawiono model danych dla wymiaru produktu Kolor. Ten sam model jest stosowany do rozmiarów, stylów i konfiguracji. 

![Model danych produktów](media/dual-write-product-two.png)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

Jeśli produkt ma różne wymiary produktu (np. produkt główny ma rozmiar i kolor jako wymiary produktu), każdy odrębny produkt (każdy wariant produktu) jest definiowany jako kombinacja tych wymiarów produktu. Na przykład numer produktu B0001 to bardzo mała czarna koszulka, a numer produktu B0002 jest małą czarną koszulką. W takim przypadku definiowane są istniejące kombinacje wymiarów produktu. Na przykład koszulka z powyższego przykładu może być bardzo mała i czarna, mała i czarna, średnia i czarna, lub duża i czarna, ale nie może być bardzo duża i czarna. Innymi słowy, wymiary produktów, które może pobrać produkt główny produktu, są określone, a warianty mogą być zwalniane na podstawie tych wartości.

Aby śledzić wymiary produktu, które może przyjąć produkt główny, w Common Data Service dla każdego wymiaru produktu są tworzone i mapowane następujące jednostki. Aby uzyskać więcej informacji, zobacz [Omówienie informacji o produktach](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Domyślne ustawienia zamówień i domyślne ustawienia zamówień charakterystyczne dla produktu

Domyślne ustawienia zamówień definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień. Te informacje będą dostępne w Common Data Service przy użyciu jednostki domyślne ustawienia zamówienia oraz jednostki domyślne ustawienia zamówienia charakterystyczne dla produktu. Możesz przeczytać więcej informacji o funkcjach na [Temacie ustawienia domyślne zamówień](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/default-order-settings).

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Jednostka miary i konwersje jednostki miary

Jednostki miary i odpowiednie konwersja jest dostępna w Common Data Service w następującym modelu danych widocznym na diagramie.

![Model danych produktów](media/dual-write-product-three.png)

Pojęcie jednostka miary jest zintegrowane między aplikacjami Finance and Operations, a innymi aplikacjami Dynamics 365. Dla każdej klasy jednostek w aplikacji Finance and Operations jest tworzona grupa jednostek w aplikacji Dynamics 365, która zawiera jednostki należące do klasy jednostek. Domyślna jednostka podstawowa jest również tworzona dla każdej grupy jednostek. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product-specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-common-data-service"></a>Początkowa synchronizacja danych jednostek pasujących między Finance and Operations i Common Data Service

### <a name="initial-synchronization-of-units"></a>Wstępna synchronizacja jednostek

Gdy włączony jest zapis podwójny, produkty z aplikacji Finance and Operations są synchronizowane i innymi aplikacjami Dynamics 365. Grupa jednostek synchronizowana z aplikacjami Finance and Operations w Common Data Service ma ustawioną flagę, która wskazuje, że są one „Zarządzane zewnętrznie”.

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Jednostki współmierne i klasy jednostek/grupy danych z Finance and Operations oraz innych aplikacji Dynamics 365

Najpierw należy pamiętać, że klucz integracji dla jednostki to msdyn_symbol. Dlatego ta wartość musi być unikatowa w Common Data Service lub innych aplikacjach systemu Dynamics 365. Ponieważ w innych aplikacjach systemu Dynamics 365 jest to para „Identyfikator grupy jednostek” i „Nazwa”, które określają unikatowość jednostki, należy wziąć pod uwagę różne scenariusze dotyczące dopasowywania danych jednostkowych między aplikacjami Finance and Operations i Common Data Service.

Dla jednostek uwzględniających/pokrywających się w aplikacjach Finance and Operations oraz inne aplikacje w ramach Dynamics 365:

+ **Jednostka należy do grupy jednostek w innych aplikacjach systemu Dynamics 365, które odpowiadają skojarzonej z nią klasom jednostek w aplikacjach Finance and Operations**. W takim przypadku pole msdyn_symbol w innych aplikacjach Dynamics 365 musi być wypełnione symbolem jednostki w aplikacje Finance and Operations. Z tego względu, gdy dane zostaną dopasowane, a grupa jednostek będzie ustawiona jako „Zarządzane zewnętrznie” w innych aplikacjach systemu Dynamics 365.
+ **Jednostka należy do grupy jednostek w innych aplikacjach systemu Dynamics 365, która nie odpowiada skojarzonej z nią klasie jednostek w aplikacjach Finance and Operations (brak istniejącej klasy jednostek w aplikacjach Finance and Operations dla klasy jednostek w innych aplikacjach Dynamics 365).** W takim przypadku msdyn_symbol musi być wypełniony ciągiem losowym. Należy zauważyć, że ta wartość musi być unikatowa lub innych aplikacjach systemu Dynamics 365.

Dla jednostek i innych klas Finance and Operations, których nie ma w innych aplikacjach Dynamics 365:

W ramach dwóch podwójnych odpisów grup jednostek z aplikacji Finance and Operations i odpowiadające im jednostki są tworzone i synchronizowane w innych aplikacjach Dynamics 365 i Common Data Service, a grupa jednostek będzie ustawiona jako „Zarządzane zewnętrznie”. Nie jest wymagany żaden dodatkowy nakład pracy inicjującej.

Dla jednostek w innych aplikacjach Dynamics 365, które nie istnieją w aplikacjach Finance and Operations:

Pole msdyn_symbol musi być wypełnione dla wszystkich jednostek. Jednostki mogą być zawsze tworzone w aplikacjach Finance and Operations w odpowiedniej klasie jednostek (jeśli istnieją). Jeśli klasa jednostek nie istnieje, najpierw należy utworzyć klasę jednostek (należy pamiętać, że nie można utworzyć klasy jednostek w aplikacjach Finance and Operations oprócz przez rozszerzenie, jeśli rozbudowuje się wyliczenie) pasujących do innych grup jednostek aplikacji Dynamics 365. Następnie można utworzyć jednostkę. Zauważ, że symbolem jednostki w aplikacjach Finance and Operations musi być msdyn_symbol poprzednio określony w innych aplikacjach Dynamics 365 dla jednostki.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Zasady dotyczące produktu: Grupa wymiarów, śledzenie i magazynowanie

Zasady dotyczące produktów to zestawy zasad używanych do definiowania produktów i ich charakterystyki w magazynie. Grupę wymiarów produktu, Grupę wymiarów śledzenia produktu i grupę wymiarów magazynowania można odnaleźć jako zasady produktu. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Hierarchie produktów

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Klucz integracji produktów 

Do unikatowego identyfikowania produktów Dynamics 365 for Finance and Operations i produktów Common Data Service są używane klucze integracji. W przypadku produktów klucz **(productnumber)** jest unikatowym kluczem identyfikującym produkt w Common Data Service. Składa się on z połączenia: **(company, msdyn_productnumber)**. **Firma** wskazuje firmę w Finance and Operations, a **msdyn_productnumber** wskazuje numer produktu dla określonego produktu w Finance and Operations. 

W przypadku użytkowników innych aplikacji Dynamics 365, produkt jest identyfikowany w interfejsie użytkownika za pomocą **msdyn_productnumber** (należy zauważyć, że etykieta pola jest **Numerem produktu**). W formularzu produktu są wyświetlane zarówno dane firmy, jak i msydn_productnumber. Niemniej jednak pole (productnumber) unikatowy klucz produktu nie jest wyświetlane. 

W przypadku konstruowania aplikacji w Common Data Service należy zwrócić uwagę na używanie **productnumber** (unikatowego identyfikatora produktu) jako klucza integracji. Nie używaj **msdyn_productnumber**, ponieważ nie jest ono unikatowe. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-common-data-service-to-finance-and-operations"></a>Wstępna synchronizacja produktów i migracja danych z Common Data Service do Finance and Operations

### <a name="initial-synchronization-of-products"></a>Wstępna synchronizacja produktów 

Gdy włączony jest zapis podwójny, produkty z aplikacji Finance and Operations są synchronizowane z Common Data Service i innymi aplikacjami opartymi na modelach w Dynamics 365. Produkty utworzone w Common Data Service i innych aplikacjach Dynamics 365 przed wydaniem podwójnego zapisywania nie będą aktualizowane ani dopasowywane do danych produktu z Finance and Operations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Dopasowywanie danych z Finance and Operations oraz innych aplikacji Dynamics 365

Jeśli te same produkty są trzymane (nakładające się/dopasowane) w Finance and Operations oraz w Common Data Service i innych aplikacjach Dynamics 365, podczas włączania podwójnego zapisywania produktów z Finance and Operations będą miały miejsce i zduplikowane rekordy pojawią się w Common Data Service dla tego samego produktu.
Aby uniknąć powyższej sytuacji, jeśli inne aplikacje w wersji Dynamics 365 mają produkty nakładające się/odpowiadają na Finance and Operations, administrator, który włącza ten proces, musi zainicjować podwójny odczyt, wybierając w polu **Firma** (na przykład: „USMF”) i **msdyn_productnumber** (na przykład: „1234:Black:S”) przed synchronizacją produktów. Innymi słowy, te dwa pola w produkcie w Common Data Service muszą być wypełnione odpowiednią firmą w Finance and Operations, do których musi zostać dopasowany produkt i jego numer produktu. 

Następnie, gdy synchronizacja zostanie włączona i ma miejsce, produkty z Finance and Operations będą synchronizowane z produktami dopasowanymi w Common Data Service i innymi aplikacjami Dynamics 365. Dotyczy to zarówno odrębnych produktów, jak i wariantów produktów. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migracja danych produktu z innych aplikacji Dynamics 365 do Finance and Operations

Jeśli inne aplikacje Dynamics 365 mają produkty, które nie są obecne w Finance and Operations, administrator może najpierw wykorzystać **EcoResReleasedProductCreationV2Entity** do importowania tych produktów do Finance and Operations. Po drugie, należy dopasować dane produktu do Finance and Operations oraz innych aplikacji Dynamics 365, tak jak opisano powyżej. 
