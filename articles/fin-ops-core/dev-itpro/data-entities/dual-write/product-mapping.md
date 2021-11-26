---
title: Ujednolicone doświadczenie korzystania z produktu
description: W tym temacie opisano integrację danych produktu między aplikacjami Finance and Operations i Dataverse.
author: t-benebo
ms.date: 12/12/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 81f49cf08dcd1b4b1c3d71ff286a1f070e65e914
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782339"
---
# <a name="unified-product-experience"></a>Ujednolicone działanie produktu

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Gdy ekosystem firmy składa się z aplikacji systemu Dynamics 365, takich jak Finance, Supply Chain Management i Sale, firmy często używają tych aplikacji do tworzenia danych produktu źródłowego. Dzieje się tak dlatego, że te aplikacje zawierają rozbudowaną infrastrukturę produktów uzupełnioną o zaawansowane koncepcje cen oraz dokładne dane o dostępnych zapasach. Firmy korzystające z systemu Product Lifecycle Management (PLM) do pozyskiwania danych produktów mogą przesyłać produkty z aplikacji Finance and Operations do innych aplikacji Dynamics 365. Ujednolicone doświadczenie korzystania z produktu w modelu danych produktów jest zintegrowane z Dataverse, dzięki czemu wszyscy użytkownicy aplikacji, w tym użytkownicy Power Platform, mogą korzystać z bogatych danych produktu pochodzących aplikacji Finance and Operations.

Oto model danych produktu z Sales.

![Model danych produktów w CE.](media/dual-write-product-4.jpg)

Oto model danych produktu z aplikacji Finance and Operations.

![Model danych produktów w Finance and Operations.](media/dual-write-products-5.jpg)

Te dwa modele danych produktu zostały zintegrowane w Dataverse w sposób przedstawiony poniżej.

![Model danych produktów w aplikacjach Dynamics 365.](media/dual-write-products-6.jpg)

Mapowania tabel podwójnego zapisywania dla produktów zostały zaprojektowane tak, aby dane były przesyłane tylko w czasie jak najbliższym rzeczywistemu z aplikacji Finance and Operations do Dataverse. Jednak infrastruktura produktów została otwarta, aby była w razie potrzeby prowadzona w sposób dwukierunkowy. Mimo że można ją dostosować na własną odpowiedzialność, ponieważ nie jest to zalecane rozwiązanie Microsoft.

## <a name="templates"></a>Szablony

Informacje o produkcie zawierają wszystkie informacje związane z produktem i jego definicję, takie jak wymiary produktu lub wymiary śledzenia i przechowywania. W poniższej tabeli przedstawiono kolekcję mapowań tabel, która umożliwia synchronizowanie produktów i informacji pokrewnych.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365 | opis
-----------------------|--------------------------------|---
[Wszystkie produkty](mapping-reference.md#138) | msdyn_globalproducts | Tabela Wszystkie produkty zawiera wszystkie produkty dostępne w aplikacjach Finance and Operations, w tym produkty zwolnione oraz produkty niezwolnione.
[Odrębne produkty zwolnione w usłudze CDS](mapping-reference.md#213) | Produkt | Tabela **Produkt** zawiera kolumny, które definiują produkt. Zawiera produkty indywidualne (produkty podtypu) i warianty produktu. Poniższa tabela przedstawia kolejność mapowań.
[Kolory](mapping-reference.md#170) | msdyn\_productcolors
[Konfiguracje](mapping-reference.md#171) | msdyn\_productconfigurations
[Ustawienia domyślne zamówień](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Kategorie produktów](mapping-reference.md#166) | msdyn_productcategories | Każda kategoria produktu oraz informacje o jego strukturze i charakterystyce znajdują się w tabeli kategorii produktów.
[Przypisania kategorii produktów](mapping-reference.md#167) | msdyn_productcategoryassignments | Aby przypisać produkt do kategorii, można użyć tabeli przypisań kategorii produktów.
[Hierarchie kategorii produktów](mapping-reference.md#168) | msdyn_productcategoryhierarchies | Hierarchie produktów umożliwiają łączenie produktów w kategorie i grupy. Hierarchie kategorii są dostępne w Dataverse przy użyciu tabeli Hierarchia kategorii produktów.
[Role hierarchii kategorii produktów](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | Hierarchie produktów mogą być używane w różnych rolach w D365 Finance and Operations. Określają, która kategoria ma być używana w każdej roli, w której jest używana tabela roli Kategoria produktu.
[Ustawienia domyślne zamówienia produktu (wersja 2)](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Grupy wymiarów produktu](mapping-reference.md#173) | msdyn\_productdimensiongroups | Grupa wymiarów produktu określa, które wymiary produktu definiują produkt.
[Kolory produktu głównego](mapping-reference.md#187) | msdyn_sharedproductcolors | Tabela **Udostępniony kolor produktu** wskazuje kolory, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Dataverse w celu zachowania spójności danych.
[Konfiguracje produktu głównego](mapping-reference.md#188) | msdyn_sharedproductconfigurations | Tabela **Udostępnione konfiguracje produktu** wskazuje konfiguracje, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Dataverse w celu zachowania spójności danych.
[Rozmiary produktu głównego](mapping-reference.md#190) | msdyn_sharedproductsizes | Tabela **Udostępniony rozmiar produktu** wskazuje rozmiary, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Dataverse w celu zachowania spójności danych.
[Style produktu głównego](mapping-reference.md#191) | msdyn_sharedproductstyles | Tabela **Udostępnione style produktu** wskazuje style, które może mieć określony produkt główny. Ta koncepcja jest migrowana w Dataverse w celu zachowania spójności danych.
[Kod kreskowy identyfikujący numer produktu](mapping-reference.md#164) | msdyn\_productbarcodes | Kody kreskowe produktów służą do jednoznacznego identyfikowania produktów.
[Konwersje jednostek specyficzne dla produktu](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Zwolnione produkty (wersja 2)](mapping-reference.md#189) | msdyn\_sharedproductdetails | Tabela **msdyn\_sharedproductdetails** zawiera pola z kolumny Finance and Operations, które definiują produkt, i zawierają informacje finansowe i informacje dotyczące zarządzania produktem.
[Rozmiary](mapping-reference.md#174) | msdyn\_productsizes
[Grupy wymiarów magazynowania](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | Grupa wymiarów magazynowania produktu reprezentuje metodę używaną do definiowania rozmieszczenia produktu w magazynie.
[Style](mapping-reference.md#178) | msdyn\_productsytles
[Grupy wymiarów śledzenia](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | Grupa wymiarów śledzenia produktu reprezentuje metodę używaną do śledzenia produktu w magazynie.
[Jednostki](mapping-reference.md#219) | uoms
[Konwersje jednostek](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>Integracja produktów

W tym modelu produkt jest reprezentowany przez kombinację dwóch tabel w Dataverse: **Produkt** i **msdyn\_sharedproductdetails**. Pierwsza tabela zawiera definicję produktu (unikatowy identyfikator produktu, nazwę produktu i opis), druga tabela zawiera kolumny przechowywane na poziomie produktu. Kombinacja tych dwóch tabel służy do definiowania produktu zgodnie z koncepcją jednostki magazynowej (SKU). Każdy zwolniony produkt będzie miał informacje zawarte w wymienionych tabelach (Szczegóły dotyczące produktu i udostępnionego produktu). Do śledzenia wszystkich produktów (zwolnionych i niezwolnionych) jest używana tabela **Produkty globalne**.

Ponieważ produkt jest reprezentowany jako jednostka SKU, pojęcia dotyczące różnych produktów, produktów głównych i wariantów produktu można przechwycić w Dataverse w następujący sposób:

- **Produkty o podtypie produktu** to produkty, które są definiowane przez siebie Nie trzeba definiować wymiarów. Przykładem jest określona księga. W przypadku tych produktów tworzony jest jeden wiersz w tabeli **Produkt** i jeden wiersz jest tworzony w tabeli **msdyn\_sharedproductdetails**. Nie utworzono wiersza rodziny produktów.
- **Produkty główne** są używane jako standardowe produkty, które posiadają definicję i reguły określające zachowanie w procesach biznesowych. Na podstawie tych definicji można generować odrębne produkty znane jako warianty produktów. Na przykład, Koszulka jest produktem głównym i może posiadać Kolor i Rozmiar jako wymiary. Można zwalniać warianty, które mają różne kombinacje tych wymiarów, np. małą, niebieską koszulkę lub średnią, zieloną koszulkę. W integracji jeden wiersz na wariant jest tworzony w tabeli produktów. Ten wiersz zawiera informacje specyficzne dla wariantu, takie jak różne wymiary. Informacje ogólne dotyczące produktu są przechowywane w tabeli **msdyn\_sharedproductdetails**. (Te ogólne informacje są przechowywane w produkcie głównym). Informacje o danych głównych produktu są synchronizowane z Dataverse z chwilą utworzenia zwolnionego produktu głównego (ale przed zwolnieniem wariantów).
- **Odrębne produkty** odnoszą się do wszystkich produktów podtypu produktu i wszystkich wariantów produktu.

![Model danych produktów.](media/dual-write-product.png)

W przypadku włączenia funkcji podwójnego zapisywania produktów z Finance and Operations zostaną zsynchronizowane w innych produktach Dynamics 365 w stanie **Wersje robocze**. Są one dodawane do pierwszego cennika w tej samej walucie, która jest używana w aplikacji spersonalizowanej obsługi odbiorców, i w kolejności alfabetycznej według nazw cennika. Innymi słowy, są dodawane do pierwszej listy cen w aplikacji Dynamics 365, która odpowiada walucie firmy z tabeli, w której produkt jest wydawany w aplikacji Finance and Operations. Jeśli nie ma cennika w danej walucie, automatycznie zostanie utworzony cennik, a produkt zostanie do niego przypisany.

Obecna implementacja wtyczek z podwójnym zapisem, które kojarzą domyślny cennik z jednostką, wyszukują walutę skojarzoną z aplikacją Finance and Operations i znajdują pierwszy cennik w aplikacji angażującej klientów przy użyciu sortowania alfabetycznego w nazwie cennika. Aby ustawić domyślny cennik dla określonej waluty, gdy masz wiele cenników dla tej waluty, musisz zaktualizować nazwę cennika do nazwy, która jest wcześniejsza w kolejności alfabetycznej niż jakiekolwiek inne cenniki dla tej samej waluty. W przypadku braku cennika w danej walucie tworzony jest nowy cennik.

Produkty domyślne z Finance and Operations operacyjnych są synchronizowane z innymi aplikacjami systemu Dynamics 365 w stanie **wersja robocza**. Aby zsynchronizować produkt z **Aktywnym** stanem, można go bezpośrednio używać w ofertach zamówień sprzedaży, na przykład należy wybrać następujące ustawienie: w obszarze **System > Administracja > Administracja systemu > Ustawienia systemu > karta Sprzedaż** wybierz opcję **Utwórz produkty w stanie aktywnym = tak**.

Jeśli produkty są synchronizowane, należy wprowadzić wartość w polu **Jednostka sprzedaży** w aplikacji Finance and Operations, ponieważ jest to pole obowiązkowe w aplikacji Sales.

Tworzenie rodzin produktów z Dynamics 365 Sales nie jest obsługiwane w przypadku synchronizacji produktów z podwójnym zapisem.

Synchronizacja produktów odbywa się z aplikacji Finance and Operations do usługi Dataverse. Oznacza to, że wartości kolumn tabeli produktu mogą być zmieniane w Dataverse, ale po wyzwoleniu synchronizacji (po zmodyfikowaniu kolumny produktu w module w aplikacji Finance and Operations) zostaną one zastąpione wartościami w Dataverse.

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Odrębne produkty zwolnione w usłudze CDS](mapping-reference.md#213) | Produkt |
[Zwolnione produkty (wersja 2)](mapping-reference.md#189) | msdyn_sharedproductdetails |
[Wszystkie produkty](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>Wymiary produktu

Wymiary produktu to cechy, które określają wariant produktu. Cztery wymiary produktu (kolor, rozmiar, styl i konfiguracja) są również mapowane w Dataverse w celu zdefiniowania wariantów produktu. Na poniższej ilustracji przedstawiono model danych dla wymiaru produktu Kolor. Ten sam model jest stosowany do rozmiarów, stylów i konfiguracji.

![Model danych dla wymiarów produktu.](media/dual-write-product-two.png)

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Kolory](mapping-reference.md#170) | msdyn\_productcolors
[Rozmiary](mapping-reference.md#174) | msdyn\_productsizes
[Style](mapping-reference.md#178) | msdyn\_productsytles
[Konfiguracje](mapping-reference.md#171) | msdyn\_productconfigurations

Jeśli produkt ma różne wymiary produktu (np. produkt główny ma rozmiar i kolor jako wymiary produktu), każdy odrębny produkt (każdy wariant produktu) jest definiowany jako kombinacja tych wymiarów produktu. Na przykład numer produktu B0001 to bardzo mała czarna koszulka, a numer produktu B0002 jest małą czarną koszulką. W takim przypadku definiowane są istniejące kombinacje wymiarów produktu. Na przykład koszulka z powyższego przykładu może być bardzo mała i czarna, mała i czarna, średnia i czarna, lub duża i czarna, ale nie może być bardzo duża i czarna. Innymi słowy, wymiary produktów, które może pobrać produkt główny produktu, są określone, a warianty mogą być zwalniane na podstawie tych wartości.

Aby śledzić wymiary produktu, które może przyjąć produkt główny, w Dataverse dla każdego wymiaru produktu są tworzone i mapowane następujące tabele. Aby uzyskać więcej informacji, zobacz [Omówienie informacji o produktach](../../../../supply-chain/pim/product-information.md).

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Kolory produktu głównego](mapping-reference.md#187) | msdyn_sharedproductcolors |
[Konfiguracje produktu głównego](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[Rozmiary produktu głównego](mapping-reference.md#190) | msdyn_sharedproductsizes |
[Style produktu głównego](mapping-reference.md#191) | msdyn_sharedproductstyles |
[Kod kreskowy identyfikujący numer produktu](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Domyślne ustawienia zamówień i domyślne ustawienia zamówień charakterystyczne dla produktu

Domyślne ustawienia zamówień definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień. Te informacje będą dostępne w Dataverse przy użyciu jednostki domyślne ustawienia zamówienia oraz jednostki domyślne ustawienia zamówienia charakterystyczne dla produktu. Możesz przeczytać więcej informacji o funkcjach na [Temacie ustawienia domyślne zamówień](../../../../supply-chain/production-control/default-order-settings.md).

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Ustawienia domyślne zamówień](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Ustawienia domyślne zamówienia produktu (wersja 2)](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Jednostka miary i konwersje jednostki miary

Jednostki miary i odpowiednia konwersja są dostępne w usłudze Dataverse w następującym modelu danych widocznym na diagramie.

![Model danych dla jednostki miary.](media/dual-write-product-three.png)

Pojęcie jednostka miary jest zintegrowane między aplikacjami Finance and Operations, a innymi aplikacjami Dynamics 365. Dla każdej klasy jednostek w aplikacji Finance and Operations jest tworzona grupa jednostek w aplikacji Dynamics 365, która zawiera jednostki należące do klasy jednostek. Domyślna jednostka podstawowa jest również tworzona dla każdej grupy jednostek.

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Konwersje jednostek specyficzne dla produktu](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Jednostki](mapping-reference.md#219) | uoms
[Konwersje jednostek](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Początkowa synchronizacja danych jednostek pasujących między Finance and Operations i Dataverse

### <a name="initial-synchronization-of-units"></a>Wstępna synchronizacja jednostek

Gdy włączony jest zapis podwójny, produkty z aplikacji Finance and Operations są synchronizowane i innymi aplikacjami Dynamics 365. Grupa jednostek synchronizowana z aplikacjami Finance and Operations w Dataverse ma ustawioną flagę, która wskazuje, że są one „Zarządzane zewnętrznie”.

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Jednostki współmierne i klasy jednostek/grupy danych z Finance and Operations oraz innych aplikacji Dynamics 365

Najpierw należy pamiętać, że klucz integracji dla jednostki to msdyn_symbol. Dlatego ta wartość musi być unikatowa w Dataverse lub innych aplikacjach systemu Dynamics 365. Ponieważ w innych aplikacjach systemu Dynamics 365 jest to para „Identyfikator grupy jednostek” i „Nazwa”, które określają unikatowość jednostki, należy wziąć pod uwagę różne scenariusze dotyczące dopasowywania danych jednostkowych między aplikacjami Finance and Operations i Dataverse.

Dla jednostek uwzględniających/pokrywających się w aplikacjach Finance and Operations oraz inne aplikacje w ramach Dynamics 365:

+ **Jednostka należy do grupy jednostek w innych aplikacjach systemu Dynamics 365, które odpowiadają skojarzonej z nią klasom jednostek w aplikacjach Finance and Operations**. W takim przypadku kolumna msdyn_symbol w innych aplikacjach Dynamics 365 musi być wypełniona symbolem jednostki w aplikacjach Finance and Operations. Z tego względu, gdy dane zostaną dopasowane, a grupa jednostek będzie ustawiona jako „Zarządzane zewnętrznie” w innych aplikacjach systemu Dynamics 365.
+ **Jednostka należy do grupy jednostek w innych aplikacjach systemu Dynamics 365, która nie odpowiada skojarzonej z nią klasie jednostek w aplikacjach Finance and Operations (brak istniejącej klasy jednostek w aplikacjach Finance and Operations dla klasy jednostek w innych aplikacjach Dynamics 365).** W takim przypadku msdyn_symbol musi być wypełniony ciągiem losowym. Należy zauważyć, że ta wartość musi być unikatowa lub innych aplikacjach systemu Dynamics 365.

Dla jednostek i innych klas Finance and Operations, których nie ma w innych aplikacjach Dynamics 365:

W ramach dwóch podwójnych odpisów grup jednostek z aplikacji Finance and Operations i odpowiadające im jednostki są tworzone i synchronizowane w innych aplikacjach Dynamics 365 i Dataverse, a grupa jednostek będzie ustawiona jako „Zarządzane zewnętrznie”. Nie jest wymagany żaden dodatkowy nakład pracy inicjującej.

Dla jednostek w innych aplikacjach Dynamics 365, które nie istnieją w aplikacjach Finance and Operations:

Kolumna msdyn_symbol musi być wypełniona dla wszystkich jednostek. Jednostki mogą być zawsze tworzone w aplikacjach Finance and Operations w odpowiedniej klasie jednostek (jeśli istnieją). Jeśli klasa jednostek nie istnieje, najpierw należy utworzyć klasę jednostek (należy pamiętać, że nie można utworzyć klasy jednostek w aplikacjach Finance and Operations oprócz przez rozszerzenie, jeśli rozbudowuje się wyliczenie) pasujących do innych grup jednostek aplikacji Dynamics 365. Następnie można utworzyć jednostkę. Zauważ, że symbolem jednostki w aplikacjach Finance and Operations musi być msdyn_symbol poprzednio określony w innych aplikacjach Dynamics 365 dla jednostki.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Zasady dotyczące produktu: Grupa wymiarów, śledzenie i magazynowanie

Zasady dotyczące produktów to zestawy zasad używanych do definiowania produktów i ich charakterystyki w magazynie. Grupę wymiarów produktu, Grupę wymiarów śledzenia produktu i grupę wymiarów magazynowania można odnaleźć jako zasady produktu.

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Grupy wymiarów produktu](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[Grupy wymiarów magazynowania](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[Grupy wymiarów śledzenia](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>Hierarchie produktów

Aplikacje Finance and Operations | Aplikacje Customer Engagement |
---|---
[Przypisania kategorii produktów](mapping-reference.md#167) | msdyn_productcategoryassignments |
[Hierarchie kategorii produktów](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[Role hierarchii kategorii produktów](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>Klucz integracji produktów

Do unikatowego identyfikowania produktów Dynamics 365 for Finance and Operations i produktów Dataverse są używane klucze integracji.
W przypadku produktów klucz **(productnumber)** jest unikatowym kluczem identyfikującym produkt w Dataverse. Składa się on z połączenia: **(company, msdyn_productnumber)**. **Firma** wskazuje firmę w Finance and Operations, a **msdyn_productnumber** wskazuje numer produktu dla określonego produktu w Finance and Operations.

W przypadku użytkowników innych aplikacji Dynamics 365, produkt jest identyfikowany w interfejsie użytkownika za pomocą **msdyn_productnumber** (należy zauważyć, że etykieta kolumny jest **Numerem produktu**). W formularzu produktu są wyświetlane zarówno dane firmy, jak i msydn_productnumber. Niemniej jednak kolumna (productnumber), unikatowy klucz produktu, nie jest wyświetlana.

W przypadku konstruowania aplikacji w Dataverse należy zwrócić uwagę na używanie **productnumber** (unikatowego identyfikatora produktu) jako klucza integracji. Nie używaj **msdyn_productnumber**, ponieważ nie jest ono unikatowe.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Wstępna synchronizacja produktów i migracja danych z Dataverse do Finance and Operations

### <a name="initial-synchronization-of-products"></a>Wstępna synchronizacja produktów

Gdy włączony jest zapis podwójny, produkty z aplikacji Finance and Operations są synchronizowane z usługą Dataverse i aplikacjami typu Customer Engagement. Produkty utworzone w Dataverse i innych aplikacjach Dynamics 365 przed wydaniem podwójnego zapisywania nie będą aktualizowane ani dopasowywane do danych produktu z Finance and Operations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Dopasowywanie danych z Finance and Operations oraz innych aplikacji Dynamics 365

Jeśli te same produkty są trzymane (nakładające się/dopasowane) w Finance and Operations oraz w Dataverse i innych aplikacjach Dynamics 365, podczas włączania podwójnego zapisywania produktów z Finance and Operations będą miały miejsce i zduplikowane wiersze pojawią się w Dataverse dla tego samego produktu.
Aby uniknąć powyższej sytuacji, jeśli inne aplikacje w wersji Dynamics 365 mają produkty nakładające się/odpowiadają na Finance and Operations, administrator, który włącza ten proces, musi zainicjować podwójny odczyt, wybierając w kolumnach **Firma** (na przykład: „USMF”) i **msdyn_productnumber** (na przykład: „1234:Black:S”) przed synchronizacją produktów. Innymi słowy, te dwie kolumny w produkcie w Dataverse muszą być wypełnione odpowiednią firmą w Finance and Operations, do których musi zostać dopasowany produkt i jego numer produktu.

Następnie, gdy synchronizacja zostanie włączona i ma miejsce, produkty z Finance and Operations będą synchronizowane z produktami dopasowanymi w Dataverse i innymi aplikacjami Dynamics 365. Dotyczy to zarówno odrębnych produktów, jak i wariantów produktów.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migracja danych produktu z innych aplikacji Dynamics 365 do Finance and Operations

Jeśli inne aplikacje Dynamics 365 mają produkty, które nie są obecne w Finance and Operations, administrator może najpierw wykorzystać **EcoResReleasedProductCreationV2Entity** do importowania tych produktów do Finance and Operations. Po drugie, należy dopasować dane produktu do Finance and Operations oraz innych aplikacji Dynamics 365, tak jak opisano powyżej.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
