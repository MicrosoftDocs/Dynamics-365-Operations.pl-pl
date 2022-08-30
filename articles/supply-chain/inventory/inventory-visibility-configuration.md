---
title: Konfiguracja dodatku Inventory Visibility
description: W tym artykule opisano sposób konfigurowania dodatku Widoczność magazynu.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 576d8d5d0cad09aed40f1ceb9ce5682816c0f666
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306327"
---
# <a name="configure-inventory-visibility"></a>Konfiguracja dodatku Inventory Visibility

[!include [banner](../includes/banner.md)]


W tym artykule opisano sposób konfigurowania widoczności magazynu za pomocą aplikacji Widoczność magazynu w usłudze Power Apps.

## <a name="introduction"></a><a name="introduction"></a>Wprowadzenie

Przed rozpoczęciem pracy z dodatkiem Widoczność magazynu należy wykonać następującą konfigurację w sposób opisany w tym artykule:

- [Konfiguracja źródła danych](#data-source-configuration)
- [Konfiguracja partycji](#partition-configuration)
- [Konfiguracja hierarchii indeksów produktów](#index-configuration)
- [Konfiguracja rezerwacji (opcjonalna)](#reservation-configuration)
- [Przykład konfiguracji standardowej](#default-configuration-sample)

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy zainstalować i skonfigurować dodatek Widoczność zapasów w sposób opisany w temacie [Instalowanie i ustawianie dodatku Widoczność magazynu](inventory-visibility-setup.md).

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>Strona konfiguracji aplikacji Widoczność magazynu

W usłudze Power Apps strona **Konfiguracja** aplikacji [Widoczność zapasów](inventory-visibility-power-platform.md) ułatwia skonfigurowanie dostępnych zapasów i rezerwacji wstępnej. Po zainstalowaniu tego dodatku domyślna konfiguracja zawiera wartość z Microsoft Dynamics 365 Supply Chain Management (źródło danych `fno`). Ustawienia domyślne można przejrzeć. Ponadto na podstawie wymagań firmy oraz wymagań księgowania zapasów w zewnętrznym systemie można zmodyfikować konfigurację w celu standaryzacji sposobu, w jaki zmiany zapasów mogą być księgowane, organizowane i wyszukiwane w różnych systemach. Pozostałe sekcje tego artykułu zawierają informacje dotyczące sposobu używania poszczególnych części strony **Konfiguracja**.

Po zakończeniu konfigurowania pamiętaj o wybraniu pozycji **Aktualizuj konfigurację** w aplikacji.

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>Włączenie funkcji Widoczność magazynu w zarządzaniu funkcjami usługi Power Apps

Dodatek Widoczność magazynu powoduje dodanie kilku nowych funkcji do instalacji usługi Power Apps. Domyślnie te funkcje są wyłączone. Aby z nich skorzystać, otwórz stronę **Konfiguracja**, a następnie na karcie **Zarządzanie funkcjami** włącz te funkcje zgodnie z potrzebami.

| Nazwa Zarządzanie funkcjami | Opis |
|---|---|
| *OnHandReservation* | Ta funkcja umożliwia tworzenie rezerwacji, rezerwacje zużycia i/lub anulowanie rezerwacji określonych ilości zapasów za pomocą funkcji Widoczność zapasów. Więcej informacji zawiera temat [Rezerwacje dodatku Widoczność magazynu](inventory-visibility-reservations.md). |
| *OnHandMostSpecificBackgroundService* | Ta funkcja zapewnia podsumowanie zapasów produktów wraz ze wszystkimi wymiarami. Dane podsumowania zapasów będą okresowo synchronizowane z aplikacją Widoczność magazynu. Domyślna częstotliwość synchronizacji jest ustawiana co 15 minut i może być ustawiana tak wysoko, jak co 5 minut. Aby uzyskać więcej informacji, zobacz [Podsumowanie inwentaryzacji](inventory-visibility-power-platform.md#inventory-summary). |
| *OnhandChangeSchedule* | Ta opcjonalna funkcja umożliwia korzystanie z funkcji harmonogramu zmian w stanie gotowości do pracy oraz dostępności do przyrzeczenia (ATP). Aby uzyskać więcej informacji, zobacz [Widoczność zapasów — harmonogram i zmiany dostępnych zapasów oraz dostępność zapasów](inventory-visibility-available-to-promise.md). |
| *Alokacja* | Dzięki tej opcjonalnej funkcji funkcja Widoczność magazynu umożliwia ochronę zapasów (ringfencing) i kontrolę nad nadmierną sprzedażą. Więcej informacji zawiera temat [Alokacja zapasów dodatku Widoczność magazynu](inventory-visibility-allocation.md). |
| *Włącz pozycje magazynowe w Widoczności magazynu* | Ta opcjonalna funkcja umożliwia widoczności zapasów obsługę pozycji, które są włączone do procesów magazynowych (pozycje WMS). Więcej informacji zawiera temat [Obsługa widoczności inwentarza dla pozycji WMS](inventory-visibility-whs-support.md). |

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Znajdowanie punktu końcowego usługi

Jeśli nie znasz prawidłowego punktu końcowego usługi Widoczność magazynu, otwórz stronę **Konfiguracja** w programie Power Apps, a następnie wybierz pozycję **Pokaż punkt końcowy usługi** w prawym górnym rogu. Na stronie zostanie pokazany prawidłowy punkt końcowy usługi.

## <a name="data-source-configuration"></a><a name="data-source-configuration"></a>Konfiguracja źródła danych

Każde źródło danych reprezentuje system, z których pochodzą dane. Przykładowe nazwy źródła danych to `fno` (co oznacza „aplikacje finansowe i operacyjne Dynamics 365”) i `pos` (co oznacza „punkt sprzedaży”). System Supply Chain Management jest ustawiany jako domyślne źródło danych (`fno`) w aplikacji Widoczność magazynu.

> [!NOTE]
> Źródło danych `fno` jest zarezerwowane dla Supply Chain Management. Jeśli dodatek Widoczność magazynu jest zintegrowany ze środowiskiem Supply Chain Management, nie zaleca się usuwania konfiguracji związanych z `fno` w źródle danych.

Procedura dodawania źródła danych jest następująca.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Źródło danych** wybierz pozycję **Nowe źródło danych**, aby dodać źródło danych.

> [!NOTE]
> Podczas dodawania źródła danych należy sprawdzić poprawność nazwy źródła danych, fizycznych miar i mapowań wymiarów przed zaktualizowaniem konfiguracji dla usługi Widoczność magazynu. Po wybraniu opcji **Aktualizuj konfigurację** nie będzie można zmodyfikować tych ustawień.

Konfiguracja źródła danych składa się z następujących części:

- Wymiary (mapowanie wymiarów)
- Fizyczne miary
- Obliczone miary

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>Wymiary (mapowanie wymiarów)

Celem konfiguracji wymiarów jest ujednolicenie integracji wielosystemowej dla księgowania zdarzeń i zapytań na podstawie kombinacji wymiarów Widoczność magazynu zawiera listę wymiarów podstawowych, które można mapować na podstawie wymiarów źródła danych. Do mapowania są dostępne 33 wymiary.

- Jeśli jednym ze źródeł danych jest Supply Chain Management, domyślnie 13 wymiarów jest mapowanych na standardowe wymiary Supply Chain Management. Pozostałych 12 wymiarów (od `inventDimension1` do `inventDimension12`) jest mapowanych na niestandardowe wymiary w Supply Chain Management. Pozostałe osiem wymiarów to wymiary rozszerzone, które można mapować na zewnętrzne źródła danych.
- Jeśli Supply Chain Management nie jest jednym ze źródeł danych, można swobodnie mapować wymiary. W poniższej tabeli pokazano pełną listę dostępnych wymiarów.

> [!NOTE]
> Jeśli wymiar nie znajduje się na liście domyślnych wymiarów i jest wykorzystywane zewnętrzne źródło danych, zaleca się mapowanie przy użyciu wymiaru od `ExtendedDimension1` do `ExtendedDimension8`.

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
| Rozszerzenie | `ExtendedDimension1` do `ExtendedDimension8` |
| System | `Empty` |

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

Procedura dodawania mapowań wymiaru jest następująca.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Źródło danych**, w sekcji **Mapowania wymiarów** wybierz pozycję **Dodaj**, aby dodać mapowania wymiarów.
    ![Dodawanie mapowań wymiarów](media/inventory-visibility-dimension-mapping.png "Dodawanie mapowań wymiarów")

1. W polu **Nazwa wymiaru** określ źródłowy wymiar.
1. W polu **Na wymiar podstawowy** wybierz wymiar w aplikacji Widoczność zapasów, który chcesz mapować.
1. Wybierz opcję **Zapisz**.

Jeśli źródło danych zawiera na przykład wymiar koloru produktu, można je mapować na wymiar podstawowy `ColorId`, aby dodać wymiar niestandardowy `ProductColor` w źródle danych `exterchannel`. Jest on wtedy mapowany na wymiar podstawowy `ColorId`.

### <a name="physical-measures"></a><a name="data-source-configuration-physical-measures"></a>Fizyczne miary

Gdy źródło danych księguje zmianę stanu zapasów do aplikacji Widoczność magazynu, zmiana ta jest księgowana przy użyciu *fizycznych miar*. Fizyczne miary modyfikują ilość i odzwierciedlają stan zapasów. W zależności od wymagań można zdefiniować własne fizyczne miary. Zapytania mogą być oparte na fizycznych miarach.

Dodatek Widoczność magazynu zawiera listę domyślnych fizycznych miar połączonych z Supply Chain Management (źródło danych `fno`). Te domyślne fizyczne miary są brane pod uwagę w stanach transakcji magazynowych na stronie **Lista dostępnych** w Supply Chain Management (**Zarządzanie zapasami \> Zapytania i raporty \> Lista dostępnych**). Przykładowe fizyczne miary są przedstawione w następującej tabeli.

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

Jeśli źródłem danych jest Supply Chain Management, nie trzeba ponownie tworzyć domyślnych fizycznych miar. Jednak w przypadku zewnętrznych źródeł danych można utworzyć nowe fizyczne miary, korzystając z poniższych kroków.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Źródło danych**, w sekcji **Miary fizyczne** wybierz opcję **Dodaj**, określ nazwę miary źródła i zapisz zmiany.

### <a name="calculated-measures"></a>Obliczone miary

Za pomocą aplikacji Widoczność magazynu można dokonywać zapytań zarówno na fizycznych miarach zapasów, jak i *niestandardowych obliczonych miarach*. Obliczone miary stanowia niestandardową formułę obliczeń, która składa się z kombinacji fizycznych miar. Funkcja ta umożliwia zdefiniowanie zestawu fizycznych miar, które będą dodawane, i/lub zestawu fizycznych miar, które będą odejmowane, aby utworzyć niestandardową miarę.

> [!IMPORTANT]
> Obliczona miara jest złożeniem miar fizycznych. Jego formuła może zawierać tylko miary fizyczne bez duplikatów, a nie miary obliczone.

Konfiguracja umożliwia zdefiniowanie zestawu modyfikatorów, które są dodawane lub odejmowane w celu uzyskania łącznej zagregowanej ilości wynikowej.

Aby skonfigurować niestandardową miarę obliczaną, należy wykonać następujące czynności.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Obliczona miara** wybierz pozycję **Nowa obliczona miara**, aby dodać obliczoną miarę.
1. Ustaw następujące pola dla nowej miary wyliczanej:

    - **Nazwa nowej miary obliczanej** — wprowadź nazwę miary obliczanej.
    - **Źródło danych** – wybierz źródło danych skojarzone z nowym modyfikatorem. Źródłem danych jest system wykonujący zapytanie.

1. Wybierz **przycisk Dodaj**, aby dodać modyfikator do nowej miary obliczanej.
1. Ustaw następujące pola dla nowego modyfikatora:

    - **Modyfikator** – Wybór typ modyfikatora (*Dodawanie* lub *Odejmowanie*).
    - **Źródło danych** – wybierz źródło danych, w którym ma zostać znaleziona miara dostarczana wartości modyfikatora.
    - **Miara** — umożliwia wybór nazwy miary (z wybranego źródła danych), która dostarcza wartość modyfikatora.

1. Powtarzaj kroki od 5 do 6, dopóki nie zostaną dodane wszystkie wymagane modyfikatory.
1. Wybierz opcję **Zapisz**.

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

Wynik `MyCustomAvailableforReservation`, oparty na ustawieniu obliczania w niestandardowych miarach, to 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>Konfiguracja partycji

Obecnie konfiguracja partycji składa się z dwóch wymiarów podstawowych (`SiteId` i `LocationId`) wskazujących sposób dystrybuowania danych. Operacje wykonywane na tej samej partycji mogą uzyskać wyższą wydajność przy niższym koszcie. Poniższa tabela wskazuje domyślną konfigurację partycji, którą zapewnia dodatek Widoczność magazynu.

| Wymiar podstawowy | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

Rozwiązanie domyślnie zawiera tę konfigurację partycji. Dlatego *nie trzeba obliczać jej ręcznie*.

> [!IMPORTANT]
> Nie dostosowuj domyślnej konfiguracji partycji. Usunięcie lub zmiana może spowodować nieoczekiwany błąd.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>Konfiguracja hierarchii indeksów produktów

Przez większość czasu zapytanie o dostępne zapasy nie będzie zwracane tylko na najwyższym poziomie „suma” Zamiast tego można także chcieć zobaczyć wyniki zagregowane na podstawie wymiarów magazynowych.

Dodatek Widoczność magazynu jest o tyle elastyczny, że umożliwia konfigurowanie _indeksów_. Indeksy te są oparte na wymiarze lub kombinacji wymiarów. Indeks składa się z *numeru zestawu*, *wymiaru* i *hierarchii*, zgodnie z następującą tabelą.

| Imię i nazwisko | opis |
|---|---|
| Numer zestawu | Wymiary należące do tego samego zestawu (indeksu) zostaną pogrupowane i zostanie im przydzielony ten sam numer zestawu. |
| Wymiar | Wymiary podstawowe, na których agregowany jest wynik zapytania. |
| Hierarchia | Hierarchia służy do definiowania obsługiwanych kombinacji wymiarów, które mogą być używane w zapytaniach. Przykładowo, można skonfigurować zestaw wymiarów z sekwencją hierarchii `(ColorId, SizeId, StyleId)`. W takim przypadku system obsługuje zapytania na kombinacjach czterech wymiarów. Pierwsza kombinacja jest pusta, druga to `(ColorId)`, trzecia to `(ColorId, SizeId)`, a czwarta `(ColorId, SizeId, StyleId)`. Inne kombinacje nie są obsługiwane. Więcej informacji można znaleźć w następujących przykładach. |

Procedura konfigurowania indeksu hierarchii produktów jest następująca.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Indeks hierarchii produktów**, w sekcji **Mapowania wymiarów** wybierz pozycję **Dodaj**, aby dodać mapowania wymiarów.
1. Domyślnie jest dostarczana lista indeksów. Aby zmodyfikować istniejący indeks, wybierz pozycję **Edytuj** lub **Dodaj** w sekcji odpowiedniego indeksu. Aby utworzyć nowy zestaw indeksów, wybierz pozycję **Nowy zestaw indeksów**. Dla każdego wiersza w każdym zestawie indeksów w polu **Wymiar** wybierz wymiar z listy wymiarów podstawowych. Wartości w następujących polach są generowane automatycznie:

    - **Numer zestawu** — wymiary należące do tej samej grupy (indeksu) zostaną pogrupowane i zostanie im przydzielony ten sam numer zestawu.
    - **Hierarchia** — hierarchia służy do definiowania obsługiwanych kombinacji wymiarów, które mogą być używane w zapytaniach w grupie wymiarów (indeksie). Jeśli na przykład zostanie skonfigurowana grupa wymiarów z sekwencją hierarchii *Styl*, *Kolor* i *Rozmiar*, system obsługuje wynik trzech grup zapytań. Pierwsza grupa to sam styl. Druga grupa to kombinacja stylu i koloru. A trzecia grupa to kombinacja stylu, koloru i rozmiaru. Inne kombinacje nie są obsługiwane.

> [!TIP]
> Poniżej podano kilka wskazówek, które należy pamiętać podczas konfigurowania hierarchii indeksów:
>
> - W konfiguracjach indeksów nie należy określać wymiarów podstawowych, które są definiowane w konfiguracji partycji. Jeśli wymiar podstawowy zostanie ponownie zdefiniowany w konfiguracji indeksu, zapytanie według tego indeksu nie będzie możliwe.
> - Jeśli potrzebne jest tylko zapytanie o stany magazynowe zagregowane według wszystkich kombinacji wymiarów, należy utworzyć pojedynczy indeks zawierający wymiar podstawowy `Empty`.
> - Musisz mieć co najmniej jedną hierarchię indeksu (na przykład zawierającą wymiar podstawowy `Empty`), w przeciwnym razie zapytania zakończą się niepowodzeniem z błędem "Nie ustawiono hierarchii indeksu".

### <a name="example"></a>Przykład

Ta sekcja zawiera przykład, który pokazuje, jak działa hierarchia.

W poniższej tabeli przedstawiono listę dostępnych zapasów w tym przykładzie.

| Pozycja | ColorId | SizeId | StyleId | Ilość |
|---|---|---|---|---|
| Koszulka | Czarny | Mały | Szeroki | 1 |
| Koszulka | Czarny | Mały | Normalne | 2 |
| Koszulka | Czarny | Duży | Szeroki | 3 |
| Koszulka | Czarny | Duży | Normalne | 4 |
| Koszulka | Czerwony | Mały | Szeroki | 5 |
| Koszulka | Czerwony | Mały | Normalne | 6 |
| Koszulka | Czerwony | Duży | Normalne | 7 |

W poniższej tabeli przedstawiono konfigurację hierarchii indeksów.

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

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>Konfiguracja rezerwacji (opcjonalna)

Konfiguracja rezerwacji jest potrzebna wtedy, gdy ma być używana funkcja rezerwacji wstępnej. Konfiguracja składa się z dwóch podstawowych części:

- Mapowanie rezerwacji wstępnej
- Hierarchia rezerwacji wstępnej

### <a name="soft-reservation-mapping"></a>Mapowanie rezerwacji wstępnej

Podczas dokonywania rezerwacji można dowiedzieć się, czy dostępne zapasy można obecnie rezerwować. Sprawdzanie poprawności jest połączone z obliczoną miarą reprezentującą formułę obliczeń kombinacji fizycznych miar.

Skonfigurowanie mapowania z fizycznej miary na obliczoną miarę umożliwia usłudze Widoczność magazynu automatyczne sprawdzanie dostępności rezerwacji na podstawie fizycznej miary.

Przed skonfigurowaniem tego mapowania fizyczne miary, obliczone miary i ich źródła danych muszą być zdefiniowane na kartach **Źródło danych** i **Obliczona miara** na stronie **Konfiguracja** w Power Apps (jak opisano wcześniej w tym artykule).

Procedura definiowania mapowania rezerwacji wstępnej jest następująca.

1. Zdefiniuj fizyczną miarę pełniącą rolę miary rezerwacji miękkiej (na przykład `SoftReservOrdered`).
1. Na karcie **Obliczona miara** na stronie **Konfiguracja** zdefiniuj obliczoną miarę *dostępne do rezerwacji* (AFR), zawierającą formułę obliczeń AFR, która ma zostać zmapowana na fizyczną miarę. Na przykład można skonfigurować miarę `AvailableToReserve` (dostępne do rezerwacji), aby była ona mapowana na wcześniej zdefiniowaną fizyczną miarę `SoftReservOrdered`. W ten sposób można stwierdzić, jakie ilości ze stanem zapasów `SoftReservOrdered` będą dostępne do rezerwacji. Poniższa tabela przedstawia formułę obliczeń AFR.

    | Typ obliczania | Źródło danych | Fizyczna miara |
    |---|---|---|
    | Dodanie | `fno` | `AvailPhysical` |
    | Dodanie | `pos` | `Inbound` |
    | Odejmowanie | `pos` | `Outbound` |
    | Odejmowanie | `iv` | `SoftReservOrdered` |

    Zaleca się skonfigurowanie miary obliczanej, tak aby zawierała miarę fizyczną, na której opiera się miara rezerwacji. W ten sposób na ilość miary obliczanej będzie wpływać ilość miary rezerwacji. Dlatego w tym przykładzie obliczona miara `AvailableToReserve` źródła danych `iv` powinna zawierać jako składnik miarę fizyczną `SoftReservOrdered` ze źródła `iv`.

1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Mapowanie rezerwacji wstępnej** należy skonfigurować mapowanie rezerwacji fizycznej na obliczoną miarę. W przypadku poprzedniego przykładu można użyć następujących ustawień, aby mapować `AvailableToReserve` na wcześniej zdefiniowaną fizyczną miarę `SoftReservOrdered`.

    | Źródło danych fizycznej miary | Fizyczna miara | Dostępne dla źródła danych rezerwacji | Dostępne dla obliczonej miary rezerwacji |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > Jeśli nie możesz edytować karty **Mapowanie rezerwacji wstępnej**, być może trzeba włączyć funkcję *OnHandReservation* na karcie **Zarządzanie funkcjami**.

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

> [!NOTE]
> Po wywołaniu interfejsu API rezerwacji można kontrolować walidacje rezerwacji, określając parametr logiczny `ifCheckAvailForReserv` w treści żądania. Wartość `True` oznacza, że walidacja jest wymagana, podczas gdy wartość `False` oznacza, że walidacja nie jest wymagana. Wartością domyślną jest `True`.

### <a name="soft-reservation-hierarchy"></a>Hierarchia rezerwacji wstępnej

Hierarchia rezerwacji opisuje sekwencję wymiarów, które muszą być określone podczas dokonywania rezerwacji. Działa to w taki sam sposób, jak hierarchia indeksów produktu w przypadku zapytań o dostępne.

Hierarchia rezerwacji jest niezależna od hierarchii indeksów produktu. Ta niezależność umożliwia wdrożenie zarządzania kategoriami, w którym użytkownicy mogą rozbić wymiary na szczegóły, aby określić wymagania dotyczące dokonywania precyzyjniejszych rezerwacji. Hierarchia rezerwacji wstępnej powinna zawierać składniki `SiteId` i `LocationId`, ponieważ konstruują one konfigurację partycji. Podczas dokonywania rezerwacji należy określić partycję produktu.

Oto przykład hierarchii rezerwacji wstępnych.

| Wymiar podstawowy | Hierarchia |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

W tym przykładzie rezerwację można wykonać w następujących sekwencjach wymiarów. Musisz określić partycję produktu podczas dokonywania rezerwacji. W związku z tym można używać hierarchii podstawowej `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

Prawidłowa sekwencja wymiarów musi ściśle naśladować hierarchię rezerwacji, wymiar po wymiarze. Na przykład sekwencja hierarchii `(SiteId, LocationId, SizeId)` jest nieprawidłowy, ponieważ brakuje w niej `ColorId`.

## <a name="available-to-promise-configuration-optional"></a>Konfiguracja dostępności zapasów (opcjonalnie)

Widoczność zapasów można skonfigurować, aby było można zaplanować przyszłe zmiany dostępnych zapasów i obliczyć ilości ATP. ATP to ilość towaru, która jest dostępna i którą można obiecać klientowi w następnym okresie. Użycie kalkulacji może znacznie zwiększyć twoje możliwości realizacji zamówień. Aby można było korzystać z tej funkcji, należy ją włączyć na karcie **Zarządzanie funkcjami**, a następnie skonfigurować na **karcie Ustawienia ATP**. Aby uzyskać więcej informacji, zobacz [Widoczność zapasów — harmonogramy i zmiany dostępnych zapasów oraz dostępność zapasów](inventory-visibility-available-to-promise.md).

## <a name="complete-and-update-the-configuration"></a>Kończenie i aktualizowanie konfiguracji

Po zakończeniu konfiguracji należy zatwierdzić wszystkie zmiany w aplikacji Widoczność magazynu. Aby zatwierdzić zmiany, wybierz pozycję **Aktualizuj konfigurację** w prawym górnym rogu strony **Konfiguracja** w Power Apps.

Po pierwszym wybraniu opcji **Aktualizuj konfigurację** system zażąda poświadczeń.

- **Identyfikator klienta** — identyfikator aplikacji systemu Azure utworzony dla aplikacji Widoczność magazynu.
- **Identyfikator dzierżawcy** — identyfikator dzierżawcy systemu Azure.
- **Klucz tajny klienta** — klucz tajny aplikacji systemu Azure utworzony dla aplikacji Widoczność magazynu.

Po zalogowaniu konfiguracja zostanie zaktualizowana w usłudze Widoczność magazynu.

> [!NOTE]
> Należy pamiętać o sprawdzeniu poprawności nazwy źródła danych, fizycznych miar i mapowań wymiarów przed zaktualizowaniem konfiguracji dla usługi Widoczność magazynu. Po wybraniu opcji **Aktualizuj konfigurację** nie będzie można zmodyfikować tych ustawień.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>Przykład konfiguracji standardowej

Na etapie inicjowania dodatek Widoczność magazynu jest ustawiony jako konfiguracja domyślna ze szczegółami podanymi w tym miejscu. Konfigurację tę można zmodyfikować stosownie do wymagań.

### <a name="data-source-configuration"></a>Konfiguracja źródła danych

#### <a name="configuration-of-the-iv-data-source"></a>Konfiguracja źródła danych iv

W tej sekcji opisano sposób konfigurowania źródła danych `iv`.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>Fizyczne miary skonfigurowane dla źródła danych „iv”

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
| Dodatek | `fno` | `ReservPhysical` |
| Dodatek | `fno` | `ReservOrdered` |
| Dodatek | `iv` | `ReservPhysical` |
| Dodatek | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>Konfiguracja źródła danych „fno”

W tej sekcji opisano sposób konfigurowania źródła danych `fno`.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>Mapowania wymiarów dla źródła danych „fno”

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

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>Fizyczne miary skonfigurowane dla źródła danych „fno”

Dla źródła danych `fno` są skonfigurowane następujące fizyczne miary:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>Konfiguracja źródła danych „pos”

W tej sekcji opisano sposób konfigurowania źródła danych `pos`.

##### <a name="physical-measures-for-the-pos-data-source"></a>Fizyczne miary dla źródła danych „pos”

Dla źródła danych `pos` są skonfigurowane następujące fizyczne miary:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>Obliczona miara AvailQuantity

Obliczona miara `AvailQuantity` jest skonfigurowana dla źródła danych `pos`, tak jak to przedstawiono w poniższej tabeli.

| Typ obliczania | Źródło danych | Fizyczna miara |
|---|---|---|
| Dodatek | `fno` | `AvailPhysical` |
| Dodatek | `pos` | `PosInbound` |
| Odejmowanie | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>Konfiguracja źródła danych „iom”

Dla źródła danych `iom` (Intelligent Order Management) są skonfigurowane następujące fizyczne miary:

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>Konfiguracja źródła danych „erp”

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

