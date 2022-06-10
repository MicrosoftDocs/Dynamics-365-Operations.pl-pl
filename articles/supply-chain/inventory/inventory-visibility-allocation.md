---
title: Widoczność zapasów Przydział zapasów
description: Ten temat wyjaśnia, jak skonfigurować i używać funkcji alokacji zapasów, która pozwala odłożyć na bok dedykowane zapasy, aby zapewnić obsługę najbardziej dochodowych kanałów lub klientów.
author: yufeihuang
ms.date: 05/20/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 4293ead4ccfc9ba04e8b9da437134b4e97569026
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786953"
---
# <a name="inventory-visibility-inventory-allocation"></a>Widoczność zapasów Przydział zapasów

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Kontekst i cel działalności

W wielu przypadkach producenci, sprzedawcy detaliczni i inni uczestnicy łańcucha dostaw muszą wstępnie przydzielić zapasy dla ważnych kanałów sprzedaży, lokalizacji, klientów lub na określone wydarzenia sprzedażowe. Przydzielanie zapasów jest typową praktyką w procesie planowania operacyjnego sprzedaży i odbywa się przed rozpoczęciem faktycznych działań sprzedażowych i utworzeniem zamówienia sprzedaży.

Na przykład firma rowerowa ma ograniczone zapasy bardzo popularnego roweru. Ta firma prowadzi zarówno sprzedaż internetową, jak i stacjonarną. W każdym kanale sprzedaży firma ma kilku ważnych partnerów korporacyjnych (rynki i dużych sprzedawców detalicznych), którzy wymagają, by określona część dostępnych zapasów roweru została zachowana właśnie dla nich. Dlatego firma rowerowa musi umieć zrównoważyć dystrybucję zapasów w różnych kanałach, a także zarządzać oczekiwaniami swoich partnerów VIP. Najlepszym sposobem na osiągnięcie obu celów jest zastosowanie przydziału zapasów, dzięki któremu każdy kanał i detalista może otrzymać określone przydzielone ilości towaru, które później mogą zostać sprzedane konsumentom.

Przydzielanie zapasów ma dwa podstawowe cele biznesowe:

- **Ochrona zapasów (ringfencing)** - Organizacje chcą wstępnie przydzielić ograniczone lub limitowane zapasy do priorytetowych kanałów, regionów, klientów VIP i spółek zależnych. Funkcja widoczności zapasów ma na celu ochronę przydzielonych zapasów, tak aby inne przydziały, rezerwacje lub inne żądania sprzedaży nie miały wpływu na wcześniej przydzielone zapasy.
- **Kontrola nad nadmierną sprzedażą** - Funkcja alokacji Widoczności zapasów ma na celu ograniczenie wcześniej alokowanych ilości, tak aby odbiorca (na przykład kanał lub grupa klientów) nie skonsumował ich nadmiernie w momencie wejścia w życie faktycznej transakcji sprzedaży opartej na rezerwacji miękkiej.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definicja alokacji w usłudze widoczności zapasów

Chociaż funkcja alokacji w usłudze Widoczności zapasów nie odkłada na bok fizycznych zapasów, to odwołuje się do dostępnych fizycznych zapasów w celu określenia początkowej *dostępnej do alokacji* ilości wirtualnej puli. Przydział zapasów w Widzialności zapasów jest przydziałem miękkim. Odbywa się to zanim dojdzie do faktycznej transakcji sprzedaży i nie zależy od zamówień sprzedaży. Na przykład, możesz przydzielić zapasy do najważniejszych kanałów sprzedaży lub dużych korporacyjnych sklepów detalicznych, zanim klienci końcowi odwiedzą dany kanał sprzedaży lub sklep detaliczny, aby je kupić.

Różnica między przydziałem zapasów a [rezerwacją miękką zapasów](inventory-visibility-reservations.md) polega na tym, że rezerwacja miękka jest zwykle powiązana z rzeczywistymi transakcjami sprzedaży (wiersze zamówień sprzedaży). Dlatego jeśli chcesz korzystać z funkcji alokacji i miękkiej rezerwacji razem, zalecamy, abyś najpierw dokonał alokacji zapasów, a następnie założył miękką rezerwę na alokowane ilości. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Użyj jako rezerwę miękką](#consume-to-soft-reserved).

Funkcja alokacji zapasów pozwala planistom sprzedaży lub menedżerom ds. kluczowych klientów zarządzać i wstępnie alokować ważne zapasy w ramach grup alokacji (takich jak kanały, regiony i grupy klientów). Umożliwia także śledzenie, korygowanie i analizowanie w czasie rzeczywistym zużycia w stosunku do przydzielonych ilości, dzięki czemu uzupełnianie lub realokacja mogą być dokonywane na czas. Możliwość obserwowania w czasie rzeczywistym alokacji, konsumpcji i salda alokacji jest szczególnie ważna podczas szybkich wyprzedaży lub promocji.

## <a name="terminology"></a>Terminologia

Poniższe terminy i pojęcia są przydatne w dyskusjach o przydziale zapasów:

- **Grupa alokacji** – Grupa, która jest właścicielem przydziału, np. kanał sprzedaży, grupa klientów lub typ zamówienia.
- **Wartość grupy alokacji** – Wartość każdej grupy alokacji. Na przykład *sieć* lub *sssklep* może być wartością grupy alokacji kanału sprzedaży, a *VIP* lub *normalny* może być wartością grupy alokacji klienta.
- **Hierarchia alokacji** – Sposób łączenia grup alokacji w sposób hierarchiczny. Na przykład możesz zdefiniować *kanał* jako poziom hierarchii 1, *region* jako poziom 2, a *grupę klientów* jako poziom 3. Podczas alokacji zapasów, gdy określasz wartość grupy alokacji, musisz przestrzegać sekwencji hierarchii alokacji. Na przykład, możesz przydzielić 200 czerwonych rowerów do kanału *sieciowego*, regionu *Londyn* i grupy klientów *VIP*.
- **Dostępna do alokacji** - *wirtualna wspólna pula*, która wskazuje ilość dostępną do dalszej alokacji. Jest to wyliczona miara, którą możesz dowolnie zdefiniować, używając własnej formuły. Jeśli korzystasz również z funkcji miękkiej rezerwacji, zalecamy, abyś użył tej samej formuły do obliczenia wartości dostępne do przydzielenia i dostępne do zarezerwowania.
- **Alokowane** – fizyczna miara pokazująca przydzieloną kwotę, która może zostać wykorzystana przez grupy alokacji.
- **Zużyte** — fizyczna miara wskazująca, że ilości zostały zużyte w odniesieniu do pierwotnie przydzielonej ilości. W miarę jak numery są dodawane do tego środka fizycznego, automatycznie zmniejsza się przydzielony środek fizyczny.

Poniższa ilustracja przedstawia przepływ pracy biznesowej dla przydziału zapasów.

![Widoczność zapasów alokacja przepływu pracy biznesowej.](media/inventory-visibility-allocation-flow.png "Widoczność zapasów alokacja przepływu pracy biznesowej.")

## <a name="set-up-inventory-allocation"></a>Ustawianie przydziału zapasów

Funkcja przydziału zapasów składa się z następujących elementów:

- Predefiniowane, związane z przydziałem źródło danych, miary fizyczne i miary obliczone.
- Dostosowywane grupy alokacji, które mogą mieć maksymalnie osiem poziomów.
- Zestaw interfejsów programowania aplikacji alokacyjnych (API):

    - allocate
    - reallocate
    - unallocate
    - consume
    - query

Proces konfigurowania funkcji alokacji składa się z dwóch kroków:

- Ustaw [źródło danych](inventory-visibility-configuration.md#data-source-configuration) i jego [środki](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Ustaw nazwę i hierarchię grupy alokacji.

### <a name="predefined-data-source"></a>Predefiniowane źródło danych

Po włączeniu funkcji alokacji i wywołaniu interfejsu API aktualizacji konfiguracji, narzędzie Widoczność zapasów tworzy jedno predefiniowane źródło danych i kilka początkowych miar.

Źródło danych nosi nazwę `@iv`.

Oto początkowe działania fizyczne:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Oto wstępnie wyliczone działania:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Dodaj inne miary fizyczne do miary obliczanej jako dostępna do przydzielenia

Aby korzystać z alokacji, musisz ustawić miarę dostępną do alokacji (`@iv`.`@available_to_allocate`). Na przykład masz źródło danych `fno` i miarę `onordered`, źródło danych `pos` i miarę `inbound` i chcesz dokonać alokacji na rękę dla sumy `fno.onordered` i `pos.inbound`. W tym przypadku `@iv.@available_to_allocate` powinno zawierać w formule `pos.inbound` i `fno.onordered`. Oto przykład:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

### <a name="change-the-allocation-group-name"></a>Zmień nazwę grupy alokacji

Można ustawić maksymalnie osiem nazw grup alokacji. Grupy mają hierarchię.

Nazwy grup ustawiasz na stronie **Konfiguracja aplikacji Power App Widoczność zapasów**. Aby otworzyć tę stronę, w swoim środowisku Microsoft Dataverse otwórz aplikację Widoczność zapasów i wybierz **Konfiguracja \> Alokacja**.

Na przykład, jeśli użyjesz czterech nazw grup i ustawisz je na \[`channel`, `customerGroup`, `region`, `orderType`\], nazwy te będą ważne dla żądań związanych z alokacją, gdy wywołasz API aktualizacji konfiguracji.

### <a name="allcoation-using-tips"></a>Wskazówki dotyczące używania alokacji

- Dla każdego produktu funkcja przydziału powinna być używana na tym samym poziomie wymiaru, zgodnie z hierarchią indeksu produktu, którą ustawisz w [konfiguracji hierarchii indeksu produktu](inventory-visibility-configuration.md#index-configuration). Na przykład hierarchia indeksu to Miejsce, Lokalizacja, Kolor, Rozmiar. Jeśli przydzielisz pewną ilość dla jednego produktu na poziomie Miejsca, Lokalizacji, Koloru. Jeśli następnym razem użyjesz do alokacji poziomu Lokalizacja, Miejsce, Kolor, jeśli użyjesz poziomu Miejsce, Miejsce, Kolor, Rozmiar lub Miejsce, Miejsce, dane nie będą spójne.
- Zmiana nazwy grupy alokacji nie będzie miała wpływu na dane zapisane w usłudze.
- Przydział powinien nastąpić, gdy produkt ma dodatnią ilość na ręku.

### <a name="using-the-allocation-api"></a><a name="using-allocation-api"></a>Używanie API alokacji

Obecnie otwartych jest pięć interfejsów API alokacji:

- POST /api/environment/{environmentId}/allocation/allocate
- POST /api/environment/{environmentId}/allocation/unallocate
- POST /api/environment/{environmentId}/allocation/reallocate
- POST /api/environment/{environmentId}/allocation/consume
- POST /api/environment/{environmentId}/allocation/query

#### <a name="allocate"></a>Przydziel

Wywołaj API `Allocate`, aby przydzielić produkt, który ma określone wymiary. Oto schemat ciała żądania.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Na przykład chcesz przydzielić 10 sztuk produktu *Rower*, miejsce *1*, lokalizację *11*, kolor *czerwony*, kanał *Online*, grupę klientów *VIP* i region *USA*. Aby dokonać tego przydziału, możesz wykonać połączenie o następującej zawartości ciała.

```json
{
    "id": "???",
    "productId": "Bike",
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 10,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

Ilość musi być zawsze większa niż 0 (zero).

#### <a name="unallocate"></a>Unallocate

Użyj API `Unallocate`, aby odwrócić operację `Allocate`. Ujemna ilość nie jest dozwolona w operacji `Allocate`. Ciało polecenia `Unallocate` jest identyczne z treścią polecenia `Allocate`.

#### <a name="reallocate"></a>Reallocate

Użyj API `Reallocate`, aby przenieść część alokowanej ilości do innej kombinacji grup. Oto schemat ciała żądania.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "sourceGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "targetGroups": {
        "groupD": "string",
        "groupE": "string",
        "groupF": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    }
}
```

Na przykład możesz przenieść dwa rowery o wymiarach \[site=1, location=11, color=red\] z grupy przydziałów \[Online, VIP, US\]do grupy przydziałów \[Online, VIP, EU\], wywołując interfejs API `Reallocate` i podając następujący tekst.

```json
{
    "id": "???",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "EU"
    },
    "quantity": 2,
    "organizationId": "usmf",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    }
}
```

#### <a name="consume"></a>Zużyj

Użyj API `Consume`, aby zamieścić informację o ilości konsumpcji w stosunku do przydziału. Na przykład możesz użyć tego API, aby przenieść przydzieloną ilość do jakiejś rzeczywistej miary. Oto schemat ciała żądania.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "targetGroups": {
        "groupA": "string",
        "groupB": "string",
        "groupC": "string"
    },
    "quantity": 0,
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "physicalMeasures": {
        "datasource1": {
            "measure": "string" // Addition or Subtraction
        }
    }
}
```

Na przykład dla grupy alokacji \[Online, VIP, US\] jest osiem przydzielonych rowerów o wymiarach \[site=1, location=11, color=red\]. Używany jest następujący wzór dostępne do alokacji:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

Osiem rowerów jest przydzielanych z miary `pos.inbound`.

Teraz sprzedawane są trzy rowery i są one pobierane z puli przydziałów. Aby zarejestrować ten ruch, możesz wykonać połączenie o następującej treści.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "pos": {
            "inbound": "Subtraction"
        }
    }
}
```

Po tym wywołaniu ilość alokowana dla produktu zostanie zmniejszona o 3. Dodatkowo Widoczność zapasów wygeneruje zdarzenie zmiany stanu posiadania, gdy `pos.inbound` = *-3*. Alternatywnie możesz zachować wartość `pos.inbound` taką, jaka jest i po prostu skonsumować przydzieloną ilość. Jednak w tym przypadku musisz albo utworzyć inną miarę fizyczną, aby zachować zużyte ilości, albo użyć miary predefiniowanej `@iv.@consumed`.

W tym żądaniu zauważ, że miara fizyczna, której używasz w treści żądania zużycia, powinna używać przeciwnego typu modyfikatora (dodawanie lub odejmowanie) niż typ modyfikatora używany dla miary obliczanej. Tak więc w tym tekście zużycia, `iv.inbound` ma wartość `Subtraction`, a nie `Addition`.

Źródło danych `fno` nie może być użyte w ciele konsumpcyjnym, ponieważ zawsze twierdziliśmy, że widoczność zapasów nie może zmienić żadnych danych w źródle danych `fno`. Przepływ danych jest jednokierunkowy, co oznacza, że wszystkie zmiany ilościowe dla źródła danych `fno` muszą pochodzić z twojego środowiska Supply Chain Management.

#### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Zużyj jako rezerwę miękką

Interfejs API `Consume` umożliwia także skonsumowanie przydzielonej ilości jako miękkiej rezerwacji. W tym przypadku operacja `Consume` zmniejszy przydzieloną ilość, a następnie dokona miękkiej rezerwacji dla tej ilości. Aby korzystać z tego podejścia, musisz także używać funkcji [miękkiej rezerwacji](inventory-visibility-reservations.md) w Widoczności zapasów.

Na przykład, ustawiłeś modyfikator rezerwacji miękkiej (środek) jako `iv.softreserved`. Do obliczania miary dostępnej rezerwy stosuje się następujący wzór:

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved`

Aby użyć tej konfiguracji z funkcją alokacji, dodaj `@iv.@allocated`do `iv.available_to_reserve`, aby otrzymać następującą formułę

`iv.available_to_reserve` = `fno.onordered` + `pos.inbound` – `iv.softreserved` – `@iv.@allocated`

Następnie zaktualizuj `@iv.@available_to_allocate` do tej samej wartości.

Jeśli chcesz skonsumować ilość 3 i bezpośrednio zarezerwować tę ilość, możesz wykonać połączenie o następującej treści.

```json
{
    "id": "???",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "targetGroups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
    "quantity": 3,
    "physicalMeasures": {
        "iv": {
            "softreserved": "Addition"
        }
    }
}
```

W tym żądaniu zwróć uwagę, że `iv.softreserved`ma wartość `Addition`, a nie `Subtraction`.

#### <a name="query"></a>Kwerenda

Użyj API `Query`, aby uzyskać informacje o przydziałach dla niektórych produktów. Możesz użyć filtrów wymiarów i filtrów grup alokacji, aby zawęzić wyniki. Wymiary muszą być dokładnie takie same, jak te, które chcesz uzyskać, na przykład \[site=1, location=11\] da niepowiązane wyniki w porównaniu z \[site=1, location=11, color=red\].

```json
{
    "productId": "string",
    "organizationId": "string",
    "dimensions": {
        "dimension1": "string",
        "dimension2": "string",
        "dimension3": "string"
    },
    "groups": {
        "additionalProp1": "string",
        "additionalProp2": "string",
        "additionalProp3": "string"
    },
}
```

Na przykład użyj \[site=1, location=11, color=red\] i pustego pola groups, aby uzyskać wszystkie rekordy alokacji:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

Użyj \[site=1, location=11, color=red\] i grupy \[channel=Online, customerGroup=VIP, region=US\], aby uzyskać rekordy alokacji dla tej grupy:

```json
{
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Online",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```
