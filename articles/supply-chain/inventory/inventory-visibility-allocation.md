---
title: Alokacja zapasów dodatku Inventory Visibility
description: Ten artykuł wyjaśnia, jak skonfigurować i używać funkcji alokacji zapasów, która pozwala odłożyć na bok dedykowane zapasy, aby zapewnić obsługę najbardziej dochodowych kanałów lub klientów.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-13
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 449ca0616405ba589b92fba1ef078a4350d1e3b1
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762680"
---
# <a name="inventory-visibility-inventory-allocation"></a>Alokacja zapasów dodatku Inventory Visibility

[!include [banner](../includes/banner.md)]

## <a name="business-background-and-purpose"></a>Kontekst i cel działalności

Organizacje często muszą wstępnie alokować swoje dostępne zapasy do najważniejszych kanałów sprzedaży, grup klientów, regionów i wydarzeń promocyjnych, aby zapewnić, że wstępnie przydzielone zapasy są chronione przed jakimkolwiek innym wykorzystaniem i mogą być wykorzystane tylko w transakcjach sprzedaży odpowiednich dla danego przydział. Alokacja zapasów w widoczności zapasów jest elementem procesu planowania operacyjnego sprzedaży i jest wykonywana przed faktycznymi działaniami sprzedażowymi lub utworzeniem zamówienia sprzedaży.

Na przykład firma o nazwie Contoso tworzy popularne dane. Niestety, ponieważ niedawne zakłócenie łańcucha dostaw wpłynęło na cały zapas tego roweru w transporcie, firma Contoso ma tylko ograniczone zapasy i musi je jak najlepiej wykorzystać. Contoso obsługuje zarówno sprzedaż online, jak i sprzedaż w sklepie. W każdym kanale sprzedaży firma ma kilku ważnych partnerów korporacyjnych (rynki i dużych sprzedawców detalicznych), którzy wymagają, by określona część dostępnych zapasów roweru została zachowana właśnie dla nich. Dlatego firma rowerowa musi umieć zrównoważyć dystrybucję zapasów w różnych kanałach, a także zarządzać oczekiwaniami swoich partnerów VIP. Najlepszym sposobem na osiągnięcie obu celów jest zastosowanie przydziału zapasów, dzięki któremu każdy kanał i detalista może otrzymać określone przydzielone ilości towaru, które później mogą zostać sprzedane konsumentom.

Przydzielanie zapasów ma dwa podstawowe cele biznesowe:

- **Ochrona zapasów (ring fencing)** - Organizacje chcą wstępnie przydzielić ograniczone lub limitowane zapasy do priorytetowych kanałów, regionów, klientów VIP i spółek zależnych. Funkcja widoczności zapasów ma na celu ochronę przydzielonych zapasów, tak aby inne przydziały, rezerwacje lub inne żądania sprzedaży nie miały wpływu na wcześniej przydzielone zapasy.
- **Kontrola nad nadmierną sprzedażą** - Funkcja alokacji Widoczności zapasów ma na celu ograniczenie wcześniej alokowanych ilości, tak aby odbiorca (na przykład kanał lub grupa klientów) nie skonsumował ich nadmiernie w momencie wejścia w życie faktycznej transakcji sprzedaży opartej na rezerwacji miękkiej.

## <a name="allocation-definition-in-inventory-visibility-service"></a>Definicja alokacji w usłudze widoczności zapasów

### <a name="allocation-virtual-pool"></a>Pula wirtualna alokacji

Chociaż funkcja alokacji w Widoczności zapasów nie odkłada na bok fizycznych zapasów, to odwołuje się do dostępnych fizycznych zapasów w celu określenia początkowej *dostępnej do alokacji* ilości wirtualnej puli. Przydział zapasów w Widzialności zapasów jest przydziałem miękkim. Odbywa się to zanim dojdzie do faktycznej transakcji sprzedaży i nie zależy od zamówień sprzedaży. Na przykład, możesz przydzielić zapasy do najważniejszych kanałów sprzedaży lub dużych korporacyjnych sklepów detalicznych, zanim klienci końcowi odwiedzą dany kanał sprzedaży lub sklep detaliczny, aby je kupić.

### <a name="difference-between-inventory-allocation-and-soft-reservation"></a>Różnica między alokacją zapasów a rezerwacją wcześniejszą

[Rezerwacje miękkie](inventory-visibility-reservations.md) są zazwyczaj związane z rzeczywistymi transakcjami sprzedaży (wiersze zamówienia sprzedaży). Zarówno alokacja, jak i rezerwacja miękka mogą być używane niezależnie, ale jeśli chcesz ich używać razem, rezerwacja miękka powinna zostać wykonana po alokacji. Zalecamy, aby najpierw wykonać alokację zapasów, a następnie miękkie rezerwowanie przydzielonych ilości, aby osiągnąć zużycie w czasie zbliżonym do alokacji. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Użyj jako rezerwę miękką](#consume-to-soft-reserved).

Funkcja alokacji zapasów pozwala planistom sprzedaży lub menedżerom ds. kluczowych klientów zarządzać i wstępnie alokować ważne zapasy w ramach grup alokacji (takich jak kanały, regiony i grupy klientów). Umożliwia także śledzenie, korygowanie i analizowanie w czasie rzeczywistym zużycia w stosunku do przydzielonych ilości, dzięki czemu uzupełnianie lub realokacja mogą być dokonywane na czas. Możliwość obserwowania w czasie rzeczywistym alokacji, konsumpcji i salda alokacji jest szczególnie ważna podczas szybkich wyprzedaży lub promocji.

## <a name="terminology"></a>Terminologia

Poniższe terminy i pojęcia są przydatne w dyskusjach o przydziale zapasów:

- **Grupa alokacji** – Grupa, która jest właścicielem przydziału, np. kanał sprzedaży, grupa klientów lub typ zamówienia.
- **Wartość grupy alokacji** – Wartość każdej grupy alokacji. Na przykład *sieć* lub *sssklep* może być wartością grupy alokacji kanału sprzedaży, a *VIP* lub *normalny* może być wartością grupy alokacji klienta.
- **Hierarchia alokacji** – Sposób łączenia grup alokacji w sposób hierarchiczny. Na przykład możesz zdefiniować *kanał* jako poziom hierarchii 1, *region* jako poziom 2, a *grupę klientów* jako poziom 3. Podczas alokacji zapasów, gdy określasz wartość grupy alokacji, musisz przestrzegać sekwencji hierarchii alokacji. Na przykład, możesz przydzielić 200 czerwonych rowerów do kanału *sieciowego*, regionu *Londyn* i grupy klientów *VIP*.
- **Dostępna do alokacji** - *wirtualna wspólna pula*, która wskazuje ilość dostępną do dalszej alokacji. Jest to wyliczona miara, którą możesz dowolnie zdefiniować, używając własnej formuły. Jeśli korzystasz również z funkcji miękkiej rezerwacji, zalecamy, abyś użył tej samej formuły do obliczenia wartości dostępne do przydzielenia i dostępne do zarezerwowania.
- **Alokowane** – fizyczna miara pokazująca przydzieloną kwotę, która może zostać wykorzystana przez grupy alokacji. Jest ona odejmowana w tym samym czasie, co ilość zużyta.
- **Zużyte** — fizyczna miara wskazująca, że ilości zostały zużyte w odniesieniu do pierwotnie przydzielonej ilości. W miarę jak numery są dodawane do tego środka fizycznego, automatycznie zmniejsza się przydzielony środek fizyczny.

Poniższa ilustracja przedstawia przepływ pracy biznesowej dla przydziału zapasów.

![Widoczność zapasów alokacja przepływu pracy biznesowej.](media/inventory-visibility-allocation-flow.png "Widoczność zapasów alokacja przepływu pracy biznesowej.")

Na poniższej ilustracji przedstawiono hierarchię alokacji i grupy alokacji. Wirtualna *wspólna pula* wyświetlana w tym miejscu to dostępna do alokacji ilość.

[<img src="media/inventory-visibility-allocation-hierarchy.png" alt="Inventory Visibility allocation hierarchy." title="Hierarchia alokacji widoczności zapasów" width="720" />](media/inventory-visibility-allocation-hierarchy.png)

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

Proces konfigurowania funkcji alokacji składa się z trzech kroków:

- Włącz funkcję w aplikacji Widoczność zapasów, przechodząc do **Konfiguracja \> Zarządzanie funkcjami i ustawienia \> Alokacja**.
- Ustaw [źródło danych](inventory-visibility-configuration.md#data-source-configuration) i jego [środki](inventory-visibility-configuration.md#data-source-configuration-physical-measures).
- Ustaw nazwę i hierarchię grupy alokacji.

### <a name="predefined-data-source"></a>Predefiniowane źródło danych

Po włączeniu funkcji alokacji i wywołaniu interfejsu API aktualizacji konfiguracji, narzędzie Widoczność zapasów tworzy jedno predefiniowane źródło danych i kilka początkowych miar.

Źródło danych nosi nazwę `@iv`. Zawiera on zestaw domyślnych miar fizycznych. Można je wyświetlić w aplikacji Widoczność zapasów, przechodząc do **Konfiguracja \> Źródło danych**. Musisz wyświetlić **źródło danych — @IV**. Rozwinięcie źródła danych `@iv` umożliwia wyświetlenie listy początkowych miar fizycznych:

- `@iv`

    - `@allocated`
    - `@cumulative_allocated`
    - `@consumed`
    - `@cumulative_consumed`

Na karcie **Obliczane miary** można wyświetlić początkową obliczoną miarę o nazwie `@iv.@available_to_allocate`:

- `@iv`

    - `@iv.@available_to_allocate` = `??` – `??` – `@iv.@allocated`

### <a name="add-other-physical-measures-to-the-available-to-allocate-calculated-measure"></a>Dodaj inne miary fizyczne do miary obliczanej jako dostępna do przydzielenia

Aby użyć alokacji, należy poprawnie skonfigurować formułę dla miary obliczeniowej dostępnej do alokacji (`@iv.@available_to_allocate`). Na przykład masz źródło danych `fno` i miarę `onordered`, źródło danych `pos` i miarę `inbound` i chcesz dokonać alokacji na rękę dla sumy `fno.onordered` i `pos.inbound`. W tym przypadku `@iv.@available_to_allocate` powinno zawierać w formule `pos.inbound` i `fno.onordered`. Oto przykład:

`@iv.@available_to_allocate` = `fno.onordered` + `pos.inbound` – `@iv.@allocated`

> [!NOTE]
> Źródło danych `@iv` jest wstępnie zdefiniowanym źródłem danych, a miary fizyczne zdefiniowane w `@iv` za pomocą prefiksu `@` są miarami wstępnie zdefiniowanymi. Te miary są wstępnie zdefiniowaną konfiguracją funkcji alokacji, więc nie należy ich zmieniać ani usuwać albo prawdopodobnie wystąpią nieoczekiwane błędy podczas korzystania z funkcji alokacji.
>
> Do wstępnie zdefiniowanej miary obliczanej można dodawać nowe miary fizyczne `@iv.@available_to_allocate`, ale nie można zmieniać ich nazwy.

### <a name="manage-allocation-groups"></a>Zarządzaj grupami alokacji

Można ustawić maksymalnie osiem nazw grup alokacji. Grupy mają hierarchię. Aby wyświetlić i zaktualizować grupy alokacji, należy wykonać następujące kroki.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**, a następnie na karcie **Alokacja** wybierz pozycję **Edytuj konfigurację**. Domyślnie istnieje hierarchia alokacji, która ma cztery warstwy: `Channel` (warstwa górna), `customerGroup` (druga warstwa), `Region` (trzecia warstwa) i `OrderType` (czwarty poziom).
1. Istniejącą grupę alokacji można usunąć, wybierając znak **X** obok tej grupy. Można również dodać nowe grupy alokacji do hierarchii, wprowadzając nazwę każdej nowej grupy bezpośrednio w polu.

    > [!IMPORTANT]
    > Podczas usuwania lub zmiany mapowania hierarchii alokacji należy zachować ostrożność. Aby uzyskać wskazówki, zobacz [Wskazówki dotyczące używania alokacji](#allocation-tips).

1. Po zakończeniu konfigurowania ustawień grupy alokacji i hierarchii alokacji zapisz zmiany, a następnie wybierz opcję **Aktualizuj konfigurację** w prawym górnym rogu. Wartości skonfigurowanych grup alokacji zostaną zaktualizowane podczas tworzenia alokacji przy użyciu interfejsu użytkownika lub API POST (/api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate). Szczegóły dotyczące obu podejść znajdują się w dalszej części tego artykułu.

Jeśli użyjesz czterech nazw grup i ustawisz je na \[`channel`, `customerGroup`, `region`, `orderType`\], nazwy te będą ważne dla żądań związanych z alokacją, gdy wywołasz API aktualizacji konfiguracji.

### <a name="tips-for-using-allocation"></a><a name="allocation-tips"></a>Wskazówki dotyczące korzystania z alokacji

- Dla każdego produktu funkcja przydziału powinna być używana na tym samym *poziomie wymiaru*, zgodnie z hierarchią indeksu produktu, którą ustawisz w [konfiguracji hierarchii indeksu produktu](inventory-visibility-configuration.md#index-configuration). Przypuśćmy na przykład, że hierarchia indeksów ma wartość \[`Site`, `Location`, `Color`, `Size`\]. Jeśli przydzieliłeś pewną ilość dla jednego produktu na poziomie wymiaru \[`Site`, `Location`, `Color`\], następnym razem, gdy będziesz chciał przydzielić ten produkt, powinieneś również przydzielić go na tym samym poziomie \[`Site`, `Location`, `Color`\]. Jeśli używasz poziomu \[`Site`, `Location`, `Color`, `Size`\] lub \[`Site`, `Location`\] dane będą niespójne.
- **Modyfikowanie grup alokacji i hierarchii:** Jeśli dane alokacji już istnieją w systemie, usunięcie istniejących grup alokacji lub zmiana w hierarchii grup alokacji spowoduje uszkodzenie istniejącego mapowania między grupami alokacji. Dlatego przed aktualizacją nowej konfiguracji należy ręcznie wyczyścić wszystkie stare dane. Jednak dodanie nowych grup alokacji do najniższej hierarchii nie ma wpływu na istniejące mapowania, nie będzie konieczne czyszczenie danych.
- Alokacja powiedzie się tylko w przypadku, gdy produkt ma ilość dodatnią `available_to_allocate`.
- Aby alokować produkty z grupy wysokiego *poziomu alokacji* do podgrupy, należy użyć interfejsu API `Reallocate`. Na przykład masz hierarchię grup przydziału \[`channel`, `customerGroup`, `region`, `orderType`\] i chcesz przydzielić jakiś produkt z grupy przydziału \[Online, VIP\] do podrzędnej grupy przydziału \[Online, VIP, EU\], użyj interfejsu API `Reallocate`, aby przenieść ilość. Jeśli użyjesz interfejsu API `Allocate`, ilość zostanie przydzielona z wirtualnej wspólnej puli.
- Aby wyświetlić ogólną dostępność produktu (wspólna pula), użyj interfejsu API [dostępnej kwerendy](inventory-visibility-api.md#query-on-hand), aby zażądać kwoty zapasów dostępnej *do alokacji*. Na podstawie tych informacji można wówczas podjąć decyzje dotyczące alokacji.

## <a name="use-the-allocation-api"></a><a name="using-allocation-api"></a>Używanie API alokacji

Obecnie otwartych jest pięć interfejsów API alokacji:

- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/allocate** — ten interfejs API służy do tworzenia początkowej alokacji.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/unallocate** – Ten interfejs API służy do cofania lub usuwania przydzielonych ilości.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/reallocate** – Ten interfejs API służy do przenoszenia przydzielonej ilości z istniejącej alokacji do innych grup alokacji.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/consume** – Ten interfejs API służy do odliczania (wykorzystania) przydzielonej ilości.
- **POST /api<wbr>/environment<wbr>/\{environmentId\}<wbr>/allocation<wbr>/query** – Ten interfejs API służy do sprawdzania istniejących rekordów alokacji względem grup i hierarchii alokacji.

### <a name="allocate"></a>Przydziel

Wywołaj API `Allocate`, aby przydzielić produkt, który ma określone wymiary. Oto schemat ciała żądania.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test101",
    "productId": "Bike",
    "groups": {
        "channel": "Web",
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

### <a name="unallocate"></a>Unallocate

Użyj API `Unallocate`, aby odwrócić operację `Allocate`. Ujemna ilość nie jest dozwolona w operacji `Allocate`. Ciało polecenia `Unallocate` jest identyczne z treścią polecenia `Allocate`.

### <a name="reallocate"></a>Reallocate

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
    "groups": {
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
    "id": "test102",
    "productId": "Bike",
    "sourceGroups": {
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
    "groups": {
        "channel": "Web",
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

### <a name="consume"></a>Zużyj

Użyj API `Consume`, aby zamieścić informację o ilości konsumpcji w stosunku do przydziału. Na przykład możesz użyć tego API, aby przenieść przydzieloną ilość do jakiejś rzeczywistej miary. Oto schemat ciała żądania.

```json
{
    "id": "string",
    "productId": "string",
    "dimensionDataSource": "string",
    "groups": {
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
    "id": "test103",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "siteId": "1",
        "locationId": "11",
        "colorId": "red"
    },
    "groups": {
        "channel": "Web",
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

W tym żądaniu należy zauważyć, że miara fizyczna użyta w treści żądania konsumpcji powinna mieć przeciwny typ modyfikatora (dodawanie lub odejmowanie) niż typ modyfikatora użyty w miarze obliczanej. Tak więc w tym tekście zużycia, `iv.inbound` ma wartość `Subtraction`, a nie `Addition`.

Źródło danych `fno` nie może być użyte w ciele konsumpcyjnym, ponieważ zawsze twierdziliśmy, że widoczność zapasów nie może zmienić żadnych danych w źródle danych `fno`. Przepływ danych jest jednokierunkowy, co oznacza, że wszystkie zmiany ilościowe dla źródła danych `fno` muszą pochodzić z twojego środowiska Supply Chain Management.

### <a name="consume-as-a-soft-reservation"></a><a name="consume-to-soft-reserved"></a>Zużyj jako rezerwę miękką

Interfejs API `Consume` umożliwia także skonsumowanie przydzielonej ilości jako miękkiej rezerwacji. W tym przypadku operacja `Consume` zmniejszy przydzieloną ilość, a następnie dokona miękkiej rezerwacji dla tej ilości. Aby korzystać z tego podejścia, musisz także używać funkcji [miękkiej rezerwacji](inventory-visibility-reservations.md) w Widoczności zapasów.

Na przykład miara fizyczna rezerwacji miękkiej została ustawiona jako `iv.softreserved`. Do obliczania miary dostępnej rezerwy stosuje się następujący wzór:

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
    "groups": {
        "channel": "Web",
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

### <a name="query"></a>Kwerenda

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
        "channel": "Web",
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
        "channel": "Web",
        "customerGroup": "VIP",
        "region": "US"
    },
}
```

## <a name="use-the-allocation-user-interface"></a>Użyj interfejsu użytkownika alokacji

Możesz ręcznie zarządzać alokacjami za pomocą interfejsu użytkownika, otwierając aplikację Widoczność zapasów i przechodząc do **Widoczność operacyjna \> Alokacja**. Stamtąd możesz wykonać dowolną z czynności opisanych w poniższych podsekcjach.

### <a name="create-an-allocation"></a>Utwórz alokację

Aby utworzyć alokację ze strony **Alokacja** aplikacji Widoczność zapasów, należy wykonać następujące kroki.

1. Wybierz opcję **Alokacja**.
1. Ustaw wartości pól podstawowych, wymiarów i docelowych grup alokacji. (Po wybraniu źródła danych zbierania w Sekcji **wymiarów** należy najpierw użyć listy rozwijanej w celu określenia wymiarów (na przykład `siteId`). Następnie wprowadź wartości wymiarów w wyświetlonych polach.)
1. Wybierz opcję **prześlij**.

### <a name="consume-an-allocation"></a>Zużyj alokację

Wybierz opcję **Zużyj**, aby zużyć alokację. Aby upewnić się, że używasz w ramach prawidłowej grupy alokacji i hierarchii, wprowadź te same zestawy szczegółów organizacji i wymiarów, które zostały wprowadzone podczas tworzenia alokacji.

### <a name="reallocate-an-allocation"></a>Ponownie przydziel alokację

Wybierz **Zmień alokację,** aby przenieść istniejącą zaalokowaną ilość z jednego zestawu grup alokacji do drugiego.

### <a name="query-existing-allocations"></a>Kwerenda dla istniejących alokacji

Wybierz **Kwerenda**, a następnie wprowadź wartości produktu, organizacji, wymiaru i grupy alokacji, aby uzyskać wyniki kwerendy dotyczącej istniejących alokacji.
