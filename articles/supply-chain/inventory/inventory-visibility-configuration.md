---
title: Konfiguracja dodatku Widoczność magazynu
description: W tym temacie opisano sposób konfigurowania dodatku Widoczność magazynu.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 92e42b22d424ab80303d771f760cfcf0599b9f4c
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345040"
---
# <a name="inventory-visibility-configuration"></a>Konfiguracja dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

W tym temacie opisano sposób konfigurowania dodatku Widoczność magazynu.

## <a name="introduction"></a><a name="introduction"></a>Wprowadzenie

Przed rozpoczęciem pracy z dodatkiem Widoczność magazynu należy wykonać następującą konfigurację w sposób opisany w tym temacie:

- [Konfiguracja źródła danych](#data-source-configuration)
- [Konfiguracja partycji](#partition-configuration)
- [Konfiguracja hierarchii indeksów produktów](#index-configuration)
- [Konfiguracja rezerwacji (opcjonalna)](#reservation-configuration)
- [Przykład konfiguracji standardowej](#default-configuration-sample)

> [!NOTE]
> Konfiguracje dodatku Widoczność magazynu można wyświetlać i edytować w programie [Microsoft Power Apps](./inventory-visibility-power-platform.md#configuration). Po zakończeniu konfigurowania wybierz pozycję **Aktualizuj konfigurację** w aplikacji.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Konfiguracja źródła danych

Źródło danych reprezentuje system, z których pochodzą dane. Mogą to być na przykład źródła `fno` (co oznacza „aplikacje Dynamics 365 Finance and Operations”) i `pos` (co oznacza „punkt sprzedaży”).

Konfiguracja źródła danych składa się z następujących części:

- Wymiar (mapowanie wymiarów)
- Fizyczna miara
- Obliczona miara

> [!NOTE]
> Źródło danych `fno` jest zarezerwowane dla Dynamics 365 Supply Chain Management.

### <a name="dimension-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Wymiar (mapowanie wymiarów)

Celem konfiguracji wymiarów jest ujednolicenie integracji wielosystemowej dla księgowania zdarzeń i zapytań na podstawie kombinacji wymiarów

Dodatek Widoczność magazynu obsługuje następujące ogólne wymiary podstawowe.

| Typ wymiaru | Wymiar podstawowy |
|---|---|
| Produkt | `ColorId` |
| Produkt | `SizeId` |
| Produkt | `StyleId` |
| Produkt | `ConfigId` |
| Śledzenie | `BatchId` |
| Śledzenie | `SerialId` |
| Lokalizacja | `LocationId` |
| Lokalizacja | `SiteId` |
| Stan zapasów | `StatusId` |
| Właściwe dla magazynu | `WMSLocationId` |
| Właściwe dla magazynu | `WMSPalletId` |
| Właściwe dla magazynu | `LicensePlateId` |
| Inne | `VersionId` |
| Magazyn (niestandardowy) | `InventDimension1` do `InventDimension12` |
| Wewnętrzny | `ExtendedDimension1` do `ExtendedDimension8` |

> [!NOTE]
> Typy wymiaru wymienione w poprzedniej tabeli służą tylko do celów informacyjnych. Nie trzeba ich definiować w dodatku Widoczność magazynu.
>
> Na potrzeby Supply Chain Management mogą być zarezerwowane wymiary magazynu (niestandardowe). W takim przypadku można używać wymiarów rozszerzonych.

Systemy zewnętrzne mogą uzyskać dostęp do dodatku Widoczność magazynu za pośrednictwem swoich interfejsów API RESTful. Na potrzeby integracji dodatek Widoczność magazynu umożliwia konfigurowanie _zewnętrznego źródła danych_ oraz mapowania _wymiarów zewnętrznych_ na _wymiary podstawowe_. Oto przykład tabeli mapowania wymiarów.

| Wymiar zewnętrzny | Wymiar podstawowy |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

Konfigurując mapowanie wymiarów, można wysyłać wymiary zewnętrzne bezpośrednio do dodatku Widoczność magazynu. Dodatek Widoczność magazynu będzie wtedy automatycznie konwertować wymiary zewnętrzne na wymiary podstawowe.

### <a name="physical-measures"></a>Fizyczne miary

Fizyczne miary modyfikują ilość i odzwierciedlają stan zapasów. W zależności od wymagań można zdefiniować własne fizyczne miary.

Dodatek Widoczność magazynu zawiera listę domyślnych fizycznych miar połączonych z Supply Chain Management (źródło danych `fno`). Przykładowe fizyczne miary są przedstawione w następującej tabeli.

| Nazwa fizycznej miary | opis |
|---|---|
| `NotSpecified` | Nieokreślona |
| `Arrived` | Dostarczone |
| `AvailOrdered` | Dostępne zamówione |
| `AvailPhysical` | Fizycznie dostępne |
| `Deducted` | Wydane |
| `OnOrder` | Na zamówienie |
| `Ordered` | Zamówiona |
| `PhysicalInvent` | Magazyn fizyczny |
| `Picked` | Pobrany |
| `PostedQty` | Zaksięgowana ilość |
| `QuotationIssue` | Oferta rozchodu |
| `QuotationReceipt` | Otrzymanie oferty |
| `Received` | Odebrane |
| `Registered` | Zarejestrowano |
| `ReservOrdered` | Zamówione i zarezerwowane |
| `ReservPhysical` | Rezerwacja fizyczna |

### <a name="calculated-measures"></a><a name="data-source-configuration-calculated-measure"></a>Obliczone miary

Obliczone miary stanowia niestandardową formułę obliczeń, która składa się z kombinacji fizycznych miar. Funkcja ta umożliwia zdefiniowanie zestawu fizycznych miar, które będą dodawane, i/lub zestawu fizycznych miar, które będą odejmowane, aby utworzyć niestandardową miarę.

Na przykład wynik zapytania może być następujący.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

Następnie należy skonfigurować obliczoną miarę o nazwie `MyCustomAvailableforReservation`, tak jak to przedstawiono w poniższej tabeli. Ta obliczona miara będzie zużywana przez system zużycia.

| System zużycia | Obliczona miara | Źródło danych | Fizyczna miara | Typ obliczania |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

Po użyciu tej formuły obliczeń nowy wynik zapytania będzie zawierał dostosowane miary.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Wynik `MyCustomAvailableforReservation`, oparty na ustawieniu obliczania w niestandardowych miarach, to 100 + 50 + 80 + 90 + 30 – 10 – 20 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Konfiguracja partycji

Konfiguracja partycji składa się z kombinacji wymiarów podstawowych. Definiuje wzorzec dystrybucji danych. Operacje na danych z tej samej partycji zapewniają wysoką wydajność i nie kosztują zbyt wiele. Dlatego dobre wzorce partycji mogą przynieść spore korzyści.

Dodatek Widoczność magazynu zawiera następującą domyślną konfigurację partycji.

| Wymiar podstawowy | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> Domyślna konfiguracja partycji ma charakter wyłącznie informacyjny. Nie trzeba jej definiować w dodatku Widoczność magazynu. Obecnie uaktualnienie konfiguracji partycji nie jest obsługiwane.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Konfiguracja hierarchii indeksów produktów

Przez większość czasu zapytanie o dostępne zapasy nie będzie zwracane tylko na najwyższym poziomie „suma” Zamiast tego można także chcieć zobaczyć wyniki zagregowane na podstawie wymiarów magazynowych.

Dodatek Widoczność magazynu jest o tyle elastyczny, że umożliwia konfigurowanie _indeksów_. Indeksy te są oparte na wymiarze lub kombinacji wymiarów. Indeks składa się z *numeru zestawu*, *wymiaru* i *hierarchii*, zgodnie z następującą tabelą.

| Imię i nazwisko | opis |
|---|---|
| Numer zestawu | Wymiary należące do tego samego zestawu (indeksu) zostaną pogrupowane i zostanie im przydzielony ten sam numer zestawu. |
| Wymiar | Wymiary podstawowe, na których agregowany jest wynik zapytania. |
| Hierarchia | Hierarchia służy do definiowania obsługiwanych kombinacji wymiarów, które mogą być używane w zapytaniach. Przykładowo, można skonfigurować zestaw wymiarów z sekwencją hierarchii `(ColorId, SizeId, StyleId)`. W takim przypadku system obsługuje zapytania na kombinacjach czterech wymiarów. Pierwsza kombinacja jest pusta, druga to `(ColorId)`, trzecia to `(ColorId, SizeId)`, a czwarta `(ColorId, SizeId, StyleId)`. Inne kombinacje nie są obsługiwane. Więcej informacji można znaleźć w następujących przykładach. |

### <a name="example"></a>Przykład

Ta sekcja zawiera przykład, który pokazuje, jak działa hierarchia.

W magazynie są następujące towary.

| Pozycja | ColorId | SizeId | StyleId | Ilość |
|---|---|---|---|---|
| Koszulka | Czarny | Mały | Szeroki | 1 |
| Koszulka | Czarny | Mały | Normalne | 2 |
| Koszulka | Czarny | Duży | Szeroki | 3 |
| Koszulka | Czarny | Duży | Normalne | 4 |
| Koszulka | Czerwony | Mały | Szeroki | 5 |
| Koszulka | Czerwony | Mały | Normalne | 6 |
| Koszulka | Czerwony | Duży | Normalne | 7 |

Oto indeks.

| Numer zestawu | Wymiar | Hierarchia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

Indeks umożliwia wykonywanie następujących zapytań o dostępne zapasy:

- `()`— pogrupowane według wszystkich

    - T-shirt, 28

- `(ColorId)`— pogrupowane według `ColorId`

    - T-shirt, czarny, 10
    - T-shirt, czerwony, 18

- `(ColorId, SizeId)`— pogrupowane według kombinacji `ColorId` i `SizeId`

    - T-shirt, czarny, S, 3
    - T-shirt, czarny, L, 7
    - T-shirt, czerwony, S, 11
    - T-shirt, czerwony, L, 7

- `(ColorId, SizeId, StyleId)`— pogrupowane według kombinacji `ColorId`, `SizeId` i `StyleId`

    - T-shirt, czarny, S, szeroki, 1
    - T-shirt, czarny, S, zwykły, 2
    - T-shirt, czarny, L, szeroki, 3
    - T-shirt, czarny, L, zwykły, 4
    - T-shirt, czerwony, S, szeroki, 5
    - T-shirt, czerwony, S, zwykły, 6
    - T-shirt, czerwony, L, zwykły, 7

> [!NOTE]
> W konfiguracjach indeksów nie należy określać wymiarów podstawowych, które są definiowane w konfiguracji partycji.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Konfiguracja rezerwacji (opcjonalna)

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Konfiguracja rezerwacji jest potrzebna wtedy, gdy ma być używana funkcja rezerwacji wstępnej. Konfiguracja składa się z dwóch podstawowych części:

- Mapowanie rezerwacji wstępnej
- Hierarchia rezerwacji wstępnej

### <a name="soft-reservation-mapping"></a>Mapowanie rezerwacji wstępnej

Podczas dokonywania rezerwacji można dowiedzieć się, czy dostępne zapasy można obecnie rezerwować. Sprawdzanie poprawności jest połączone z obliczoną miarą reprezentującą formułę obliczeń kombinacji fizycznych miar.

Na przykład miara rezerwacji może być oparta na fizycznej mierze `SoftReservOrdered` ze źródła danych `iv` (Widoczność magazynu). W takim przypadku można skonfigurować obliczoną miarę `AvailableToReserve` źródła danych `iv`, jak pokazano w tym miejscu.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `AvailPhysical` |
| Dodanie | `pos` | `Inbound` |
| Odejmowanie | `pos` | `Outbound` |
| Odejmowanie | `iv` | `SoftReservOrdered` |

Następnie należy skonfigurować mapowanie rezerwacji wstępnej, aby utworzyć mapowanie miary rezerwacji `SoftReservOrdered` na obliczoną miarę `AvailableToReserve`.

| Źródło danych fizycznej miary | Fizyczna miara | Dostępne dla źródła danych rezerwacji | Dostępne dla obliczonej miary rezerwacji |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

Teraz podczas dokonywania rezerwacji na `SoftReservOrdered` dodatek Widoczność magazynu będzie automatycznie znajdować `AvailableToReserve` i jego powiązaną formułę obliczeń w celu sprawdzania poprawności rezerwacji.

W dodatku Widoczność magazynu mogą być widoczne na przykład następujące dostępne zapasy.

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

W takim przypadku ma zastosowanie następujące obliczenie:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

Jeśli zatem po próbie dokonania rezerwacji na `iv.SoftReservOrdered` ilość jest mniejsza lub równa `AvailableToReserve` (10), można wykonać rezerwację.

### <a name="soft-reservation-hierarchy"></a>Hierarchia rezerwacji wstępnej

Hierarchia rezerwacji opisuje sekwencję wymiarów, które muszą być określone podczas dokonywania rezerwacji. Działa to w taki sam sposób, jak hierarchia indeksów produktu w przypadku zapytań o dostępne.

Hierarchia rezerwacji jest niezależna od hierarchii indeksów produktu. Ta niezależność umożliwia wdrożenie zarządzania kategoriami, w którym użytkownicy mogą rozbić wymiary na szczegóły, aby określić wymagania dotyczące dokonywania precyzyjniejszych rezerwacji.

Oto przykład hierarchii rezerwacji wstępnych.

| Wymiar podstawowy | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

W tym przykładzie rezerwację można wykonać w następujących sekwencjach wymiarów:

- `()`— nie określono wymiaru.
- `(SiteId)`
- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Prawidłowa sekwencja wymiarów musi ściśle naśladować hierarchię rezerwacji, wymiar po wymiarze. Na przykład sekwencja hierarchii `(SiteId, LocationId, SizeId)` jest nieprawidłowy, ponieważ brakuje w niej `ColorId`.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Przykład konfiguracji standardowej

Na etapie inicjowania dodatek Widoczność magazynu odznacza się domyślną konfiguracją. Konfigurację można zmodyfikować stosownie do wymagań.

### <a name="data-source-configuration"></a>Konfiguracja źródła danych

#### <a name="configuration-of-the-iv-data-source"></a>Konfiguracja źródła danych iv

W tej sekcji opisano sposób konfigurowania źródła danych `iv`.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Fizyczne miary skonfigurowane dla źródła danych iv

Dla źródła danych `iv` są skonfigurowane następujące fizyczne miary:

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>Obliczona miara OrderedTotal

Obliczona miara `OrderedTotal` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `Ordered` |
| Dodanie | `fno` | `Arrived` |
| Dodanie | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>Obliczona miara OnHand

Obliczona miara `OnHand` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `PhysicalInvent` |
| Dodanie | `iom` | `OnHand` |
| Dodanie | `erp` | `Unrestricted` |
| Dodanie | `erp` | `QualityInspection` |
| Dodanie | `pos` | `PosInbound` |
| Odejmowanie | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>Obliczona miara ReservedTotal

Obliczona miara `ReservedTotal` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `ReservPhysical` |
| Dodanie | `fno` | `ReservOrdered` |
| Dodanie | `iv` | `SoftReservPhysical` |
| Dodanie | `iv` | `SoftReservOrdered` |
| Dodanie | `iv` | `ReservPhysical` |
| Dodanie | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>Obliczona miara SoftReserved

Obliczona miara `SoftReserved` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `iv` | `SoftReservPhysical` |
| Dodanie | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>Obliczona miara HardReserved

Obliczona miara `HardReserved` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `ReservPhysical` |
| Dodanie | `fno` | `ReservOrdered` |
| Dodanie | `iv` | `ReservPhysical` |
| Dodanie | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>Obliczona miara OpenOrder

Obliczona miara `OpenOrder` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `OnOrder` |
| Dodanie | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>Obliczona miara OnHandAvailable

Obliczona miara `OnHandAvailable` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `PhysicalInvent` |
| Dodanie | `iom` | `OnHand` |
| Dodanie | `erp` | `Unrestricted` |
| Dodanie | `erp` | `QualityInspection` |
| Dodanie | `pos` | `PosInbound` |
| Odejmowanie | `fno` | `ReservPhysical` |
| Odejmowanie | `iv` | `SoftReservPhysical` |
| Odejmowanie | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>Obliczona miara AvailableToReserve

Obliczona miara `AvailableToReserve` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `PhysicalInvent` |
| Dodanie | `iom` | `OnHand` |
| Dodanie | `erp` | `Unrestricted` |
| Dodanie | `erp` | `QualityInspection` |
| Dodanie | `pos` | `PosInbound` |
| Dodanie | `fno` | `Ordered` |
| Dodanie | `fno` | `Arrived` |
| Dodanie | `iv` | `Ordered` |
| Odejmowanie | `fno` | `ReservPhysical` |
| Odejmowanie | `fno` | `ReservOrdered` |
| Odejmowanie | `iv` | `SoftReservPhysical` |
| Odejmowanie | `iv` | `SoftReservOrdered` |
| Odejmowanie | `iv` | `ReservPhysical` |
| Odejmowanie | `iv` | `ReservOrdered` |
| Odejmowanie | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>Obliczona miara InventorySupply

Obliczona miara `InventorySupply` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `Ordered` |
| Dodanie | `fno` | `Arrived` |
| Dodanie | `iv` | `Ordered` |
| Dodanie | `fno` | `PhysicalInvent` |
| Dodanie | `iom` | `OnHand` |
| Dodanie | `erp` | `Unrestricted` |
| Dodanie | `erp` | `QualityInspection` |
| Dodanie | `pos` | `PosInbound` |
| Odejmowanie | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>Obliczona miara InventoryDemand

Obliczona miara `InventoryDemand` jest skonfigurowana dla źródła danych `iv`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `OnOrder` |
| Dodanie | `iom` | `OnOrder` |
| Dodanie | `iv` | `SoftReservPhysical` |
| Dodanie | `iv` | `SoftReservOrdered` |
| Dodanie | `fno` | `ReservPhysical` |
| Dodanie | `fno` | `ReservOrdered` |
| Dodanie | `iv` | `ReservPhysical` |
| Dodanie | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Konfiguracja źródła danych fno

W tej sekcji opisano sposób konfigurowania źródła danych `fno`.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mapowania wymiarów dla źródła danych fno

Mapowania wymiarów wyszczególnione w następującej tabeli są skonfigurowane dla źródła danych `fno`.

| Wymiar zewnętrzny | Wymiar podstawowy |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Fizyczne miary skonfigurowane dla źródła danych fno

Dla źródła danych `fno` są skonfigurowane następujące fizyczne miary:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Konfiguracja źródła danych pos

W tej sekcji opisano sposób konfigurowania źródła danych `pos`.

##### <a name="physical-measures-for-the-pos-data-source"></a>Fizyczne miary dla źródła danych pos

Dla źródła danych `pos` są skonfigurowane następujące fizyczne miary:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Obliczona miara AvailQuantity

Obliczona miara `AvailQuantity` jest skonfigurowana dla źródła danych `pos`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodanie | `fno` | `AvailPhysical` |
| Dodanie | `pos` | `PosInbound` |
| Odejmowanie | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Konfiguracja źródła danych iom

Dla źródła danych `iom` (Intelligent Order Management) są skonfigurowane następujące fizyczne miary:

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Konfiguracja źródła danych erp

Dla źródła danych `erp` (planowanie zasobów przedsiębiorstwa) są skonfigurowane następujące fizyczne miary:

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>Konfiguracja partycji

Domyślna konfiguracja partycji jest przedstawiona w następującej tabeli.

| Wymiar podstawowy | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>Konfiguracja indeksu

Domyślna konfiguracja indeksu jest przedstawiona w następującej tabeli.

| Numer zestawu | Wymiar | Hierarchia |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>Konfiguracja rezerwacji

W tej sekcji opisano domyślną konfigurację rezerwacji.

#### <a name="reservation-mapping"></a>Mapowanie rezerwacji

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Domyślne mapowanie rezerwacji jest przedstawione w następującej tabeli.

| Źródło danych fizycznej miary | Fizyczna miara | Dostępne dla źródła danych rezerwacji | Dostępne dla obliczonej miary rezerwacji |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>Hierarchia rezerwacji

Domyślna hierarchia rezerwacji jest przedstawiona w następującej tabeli.

| Wymiar podstawowy | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
