---
title: Aplikacja Widoczność magazynu
description: W tym temacie opisano sposób korzystania z aplikacji Widoczność magazynu.
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
ms.openlocfilehash: cc09dd82547ec42041889e9a96662cd17549a3ea
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345009"
---
# <a name="inventory-visibility-app"></a>Aplikacja Widoczność magazynu

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

W tym temacie opisano sposób korzystania z aplikacji Widoczność magazynu.

Widoczność magazynu to aplikacja oparta na modelu służąca do wizualizacji. Aplikacja zawiera trzy strony: **Konfiguracja**, **Widoczność operacyjna** i **Podsumowanie zapasów**. Jej właściwości są następujące

- Zawiera interfejs użytkownika (UI) do konfigurowania rezerwacji dostępnych zapasów i konfigurowania rezerwacji wstępnej.
- Obsługuje zapytania o dostępne zapasy w czasie rzeczywistym dla różnych kombinacji wymiarów.
- Zawiera interfejs użytkownika do księgowania żądań rezerwacji.
- Zapewnia spersonalizowany widok dostępnych zapasów produktów wraz ze wszystkimi wymiarami

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy zainstalować i skonfigurować dodatek Widoczność zapasów w sposób opisany w temacie [Ustawianie dodatku Widoczność magazynu](inventory-visibility-setup.md).

## <a name="configuration"></a><a name="configuration"></a>Konfiguracja

Strona **Konfiguracja** ułatwia skonfigurowanie dostępnych zapasów i rezerwacji wstępnej. Po zainstalowaniu tego dodatku domyślna konfiguracja zawiera wartość z Microsoft Dynamics 365 Supply Chain Management (źródło danych `fno`). Ustawienie domyślne można przejrzeć. Ponadto na podstawie wymagań firmy oraz wymagań księgowania zapasów w zewnętrznym systemie można zmodyfikować konfigurację w [Dataverse](/powerapps/maker/common-data-service/data-platform-intro) w celu standaryzacji sposobu, w jaki zmiany zapasów mogą być księgowane, organizowane i wyszukiwane w różnych systemach.

### <a name="define-data-sources"></a>Definiowanie źródeł danych

Użytkownik definiuje każde *źródło danych*, które ma zostać zintegrowane z aplikacją Widoczność magazynu. Widoczność magazynu obsługuje integrację z różnymi źródłami danych, takimi jak system punktu sprzedaży (POS), Supply Chain Management i inne systemy zewnętrzne. System Supply Chain Management jest ustawiany jako domyślne źródło danych (`fno`) w aplikacji Widoczność magazynu.

Procedura dodawania źródła danych jest następująca.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Źródło danych** wybierz pozycję **Nowe źródło danych**, aby dodać źródło danych.

> [!NOTE]
> Podczas dodawania źródła danych należy sprawdzić poprawność nazwy źródła danych, fizycznych miar i mapowań wymiarów przed zaktualizowaniem konfiguracji dla usługi Widoczność magazynu. Po wybraniu opcji **Aktualizuj konfigurację** nie będzie można zmodyfikować tych ustawień.

### <a name="set-up-dimension-mappings"></a>Konfigurowanie mapowań wymiarów

Widoczność magazynu zawiera listę wymiarów podstawowych, które można mapować na podstawie wymiarów źródła danych. Do mapowania są dostępne 33 wymiary.

- Jeśli jednym ze źródeł danych jest Supply Chain Management, domyślnie 13 wymiarów jest mapowanych na standardowe wymiary Supply Chain Management. Pozostałych 12 wymiarów (od `inventDimension1` do `inventDimension12`) jest mapowanych na niestandardowe wymiary w Supply Chain Management. Pozostałe osiem wymiarów to wymiary rozszerzone, które można mapować na zewnętrzne źródła danych.
- Jeśli Supply Chain Management nie jest jednym ze źródeł danych, można swobodnie mapować wymiary. W poniższej tabeli pokazano pełną listę dostępnych wymiarów.

> [!NOTE]
> Jeśli wymiar nie znajduje się na liście domyślnych wymiarów i jest wykorzystywane zewnętrzne źródło danych, zaleca się mapowanie przy użyciu wymiaru od `ExtendedDimension1` do `ExtendedDimension8`.

| Typ wymiaru | Nazwa wymiaru |
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
| Inna | `VersionId` |
| Magazyn (niestandardowy) | `InventDimension1` do `InventDimension12` |
| Inna | `ExtendedDimension1` do `ExtendedDimension8` |

Procedura dodawania mapowań wymiaru jest następująca.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Źródło danych**, w sekcji **Mapowania wymiarów** wybierz pozycję **Dodaj**, aby dodać mapowania wymiarów.
1. W polu **Nazwa wymiaru** określ źródłowy wymiar.
1. W polu **Na wymiar podstawowy** wybierz wymiar w aplikacji Widoczność zapasów, który chcesz mapować.
1. Wybierz opcję **Zapisz**.

![Dodawanie mapowań wymiarów](media/inventory-visibility-dimension-mapping.png "Dodawanie mapowań wymiarów")

Jeśli źródło danych zawiera na przykład wymiar koloru produktu, można je mapować na wymiar podstawowy `ColorId`, aby dodać wymiar niestandardowy `ProductColor` w źródle danych `exterchannel`. Jest on wtedy mapowany na wymiar podstawowy `ColorId`.

## <a name="create-a-physical-measure"></a>Tworzenie fizycznej miary

Gdy źródło danych księguje zmianę stanu zapasów do aplikacji Widoczność magazynu, zmiana ta jest księgowana przy użyciu *fizycznych miar*. Fizyczne miary są modyfikatorami odzwierciedlający podsumowane stany transakcji magazynowych. Zapytania mogą być oparte na fizycznych miarach.

Widoczność magazynu zawiera listę domyślnych fizycznych miar. Te domyślne fizyczne miary są brane pod uwagę w stanach transakcji magazynowych na stronie **Lista dostępnych** w Supply Chain Management (**Zarządzanie zapasami \> Zapytania i raporty \> Lista dostępnych**).

| Modyfikator | Imię i nazwisko |
|---|---|
| `PhysicalInvent` | Magazyn fizyczny |
| `ReservPhysical` | Fizyczne zarezerwowane |
| `AvailPhysical` | Fizycznie dostępne |
| `ReservOrdered` | Zamówione zarezerwowane |
| `PostedQty` | Zaksięgowana ilość |
| `Deducted` | Wydane |
| `Picked` | Pobrany |
| `Received` | Odebrane |
| `Registered` | Zarejestrowano |
| `Arrived` | Dostarczone |
| `Ordered` | Zamówiona |
| `OnOrder` | Na zamówienie |
| `QuotationReceipt` | Otrzymanie oferty |
| `QuotationIssue` | Wydanie oferty |

Jeśli źródłem danych jest Supply Chain Management, nie trzeba ponownie tworzyć domyślnych fizycznych miar. Jednak w przypadku zewnętrznych źródeł danych można utworzyć nowe fizyczne miary, korzystając z poniższych kroków.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Źródło danych**, w sekcji **Miary fizyczne** wybierz opcję **Dodaj**, określ nazwę miary źródła i zapisz zmiany.

## <a name="define-the-product-hierarchy-index"></a>Definiowanie indeksu hierarchii produktów

Ustawiając zagregowane grupy wymiarów, można używać aplikacji Widoczność magazynu do wykonywania zapytania o stan dostępnych zapasów. W aplikacji Widoczność magazynu każda grupa wymiarów jest nazywana *indeksem*. Każdy indeks odpowiada numerowi zestawu. Na podstawie sposobu wykonywania zapytań w aplikacji Widoczność magazynu można określić, które wymiary będą używane do konfigurowania indeksowania.

Procedura konfigurowania indeksu hierarchii produktów jest następująca.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Indeks hierarchii produktów**, w sekcji **Mapowania wymiarów** wybierz pozycję **Dodaj**, aby dodać mapowania wymiarów.
1. Domyślnie jest dostarczana lista indeksów. Aby zmodyfikować istniejący indeks, wybierz pozycję **Edytuj** lub **Dodaj** w sekcji odpowiedniego indeksu. Aby utworzyć nowy zestaw indeksów, wybierz pozycję **Nowy zestaw indeksów**. Dla każdego wiersza w każdym zestawie indeksów w polu **Wymiar** wybierz wymiar z listy wymiarów podstawowych. Wartości w następujących polach są generowane automatycznie:

    - **Numer zestawu** — wymiary należące do tej samej grupy (indeksu) zostaną pogrupowane i zostanie im przydzielony ten sam numer zestawu.
    - **Hierarchia** — hierarchia służy do definiowania obsługiwanych kombinacji wymiarów, które mogą być używane w zapytaniach w grupie wymiarów (indeksie). Jeśli na przykład zostanie skonfigurowana grupa wymiarów z sekwencją hierarchii *Styl*, *Kolor* i *Rozmiar*, system obsługuje wynik trzech grup zapytań. Pierwsza grupa to sam styl. Druga grupa to kombinacja stylu i koloru. A trzecia grupa to kombinacja stylu, koloru i rozmiaru. Inne kombinacje nie są obsługiwane.

Więcej informacji można znaleźć w temacie [Konfiguracja hierarchii indeksów produktów](inventory-visibility-configuration.md#index-configuration).

### <a name="example"></a>Przykład

Ta sekcja zawiera przykład, który pokazuje, jak działa hierarchia. W poniższej tabeli przedstawiono listę dostępnych zapasów w tym przykładzie.

| Pozycja | Styl | Kolor | Rozmiar | Ilość |
|---|---|---|---|---|
| I0001 | Szeroki | Czarny | Mały | 1 |
| I0001 | Szeroki | Czarny | Duży | 2 |
| I0001 | Szeroki | Czerwony | Mały | 3 |
| I0001 | Normalne | Czarny | Mały | 4 |
| I0001 | Normalne | Czarny | Duży | 5 |
| I0001 | Normalne | Czerwony | Mały | 6 |
| I0001 | Normalne | Czerwony | Duży | 7 |

W poniższej tabeli przedstawiono konfigurację hierarchii indeksów.

| Klucz | Numer zestawu | Hierarchia |
|---|---|---|
| `StyleId` | 1 | 1 |
| `ColorId` | 1 | 2 |
| `SizeId` | 1 | 3 |

Na podstawie poprzednich ustawień kombinacją wymiarów zapytania aplikacji Widoczność magazynu jest *Styl*, *Kolor* i *Rozmiar*. Konfiguracja hierarchii umożliwia wykonywanie następujących zapytań o dostępne zapasy przez zewnętrzne systemy:

- `()`— pogrupowane według wszystkich. Oto wynik:

    - I0001, 28

- `(StyleId)` — grupowanie według stylów. Oto wynik:

    - I0001, szeroki, 6
    - I0001, zwykły, 22

- `(StyleId, ColorId)`— pogrupowane według kombinacji stylu i koloru. Oto wynik:

    - I0001, szeroki, czarny,3
    - I0001, szeroki, czerwony, 3
    - I0001, zwykły, czarny, 9
    - I0001, zwykły, czerwony, 13

- `(StyleId, ColorId, SizeId)`— pogrupowane według kombinacji stylu, koloru i rozmiaru. Oto wynik:

    - I0001, szeroki, czarny, S,1
    - I0001, szeroki, czarny, L, 2
    - I0001, szeroki, czerwony, S, 3
    - I0001, zwykły, czarny, S, 4
    - I0001, zwykły, czarny, L, 5
    - I0001, zwykły, czerwony, S, 6
    - I0001, zwykły, czerwony, L, 7

## <a name="set-up-a-custom-calculated-measure"></a>Konfigurowanie niestandardowej obliczanej miary

Za pomocą aplikacji Widoczność magazynu można dokonywać zapytań zarówno na fizycznych miarach zapasów, jak i *niestandardowych obliczonych miarach*.

Konfiguracja umożliwia zdefiniowanie zestawu modyfikatorów, które są dodawane lub odejmowane w celu uzyskania łącznej zagregowanej ilości wynikowej.

1. Zaloguj się do swojego środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Obliczona miara** wybierz pozycję **Nowa obliczona miara**, aby dodać obliczoną miarę. Następnie ustaw pola, które są opisane w następującej tabeli.

    | Pole | Wartość |
    |---|---|
    | Nazwa nowej obliczonej miary | Umożliwia wprowadzenie nazwy obliczonej miary. |
    | Źródło danych | Źródłem danych jest system wykonujący zapytanie. |
    | Źródło danych modyfikatora | Umożliwia wprowadzenie źródła danych modyfikatora. |
    | Modyfikator | Umożliwia wprowadzenie nazwy modyfikatora. |
    | Typ modyfikatora | Wybór typ modyfikatora (*Dodawanie* lub *Odejmowanie*). |

W poniższej tabeli przedstawiono przykładową niestandardową obliczoną miarę `MyCustomAvailableforReservation`. Aby uzyskać więcej informacji o tym przykładzie, zobacz temat [Konfiguracja źródła danych](inventory-visibility-configuration.md#data-source-configuration).

| Źródło danych obliczonej miary | Obliczona miara | Źródło danych modyfikatora | Modyfikator | Typ modyfikatora |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `Outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `Exteexterchannelrchannel` | `reserved` | `Subtraction` |

### <a name="set-up-a-soft-reservation-mapping"></a><a name="setup-reservation-mapping"></a>Konfigurowanie mapowania rezerwacji wstępnej

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Przed przystąpieniem do edytowania karty **Mapowanie rezerwacji wstępnej** należy włączyć funkcję *OnHandReservation* na karcie **Zarządzanie funkcjami**.

Skonfigurowanie mapowania z fizycznej miary na obliczoną miarę umożliwia usłudze Widoczność magazynu automatyczne sprawdzanie dostępności rezerwacji na podstawie fizycznej miary.

Przed skonfigurowaniem tego mapowania fizyczne miary, obliczone miary i ich źródła danych muszą być zdefiniowane na kartach **Źródło danych** i **Obliczona miara** na stronie **Konfiguracja** w Power Apps (jak opisano wcześniej w tym temacie).

Procedura definiowania mapowania rezerwacji wstępnej jest następująca.

1. Zdefiniuj fizyczną miarę pełniącą rolę miary rezerwacji miękkiej (na przykład `softreservordered`).
1. Na karcie **Obliczona miara** na stronie **Konfiguracja** zdefiniuj obliczoną miarę *dostępne do rezerwacji* (AFR), zawierającą formułę obliczeń AFR, która ma zostać zmapowana na fizyczną miarę. Na przykład można skonfigurować miarę `availforreserv` (dostępne do rezerwacji), aby była ona mapowana na wcześniej zdefiniowaną fizyczną miarę `softreservordered`. W ten sposób można stwierdzić, jakie ilości ze stanem zapasów `softreservordered` będą dostępne do rezerwacji. Poniższa tabela przedstawia formułę obliczeń AFR.

    | Modyfikator | Źródło danych | Miara |
    |---|---|---|
    | `Addition` | `fno` | `availphysical` |
    | `Addition` | `pos` | `inbound` |
    | `Subtraction` | `pos` | `outbound` |
    | `Subtraction` | `iv` | `softreservordered` |

1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Mapowanie rezerwacji wstępnej** należy skonfigurować mapowanie rezerwacji fizycznej na obliczoną miarę. W przypadku poprzedniego przykładu można użyć następujących ustawień, aby mapować `availforreserv` na wcześniej zdefiniowaną fizyczną miarę `softreservordered`.

    | Źródło danych fizycznej miary | Fizyczna miara | Dostępne dla źródła danych rezerwacji | Dostępne dla obliczonej miary rezerwacji |
    |---|---|---|---|
    | `iv` | `softreservordered` | `iv` | `availforreserv` |

### <a name="set-up-a-soft-reservation-hierarchy"></a><a name="setup-reservation-hierarchy"></a>Konfigurowanie hierarchii rezerwacji wstępnej

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Przed przystąpieniem do edytowania karty **Hierarchia rezerwacji wstępnej** należy włączyć funkcję *OnHandReservation* na karcie **Zarządzanie funkcjami**.

Hierarchia rezerwacji opisuje sekwencję wymiarów, które muszą być określone podczas dokonywania rezerwacji. Działa to w taki sam sposób, jak hierarchia indeksów produktu w przypadku zapytań o dostępne.

Hierarchia rezerwacji może się różnić od hierarchii indeksów dostępnych zapasów. Ta niezależność umożliwia wdrożenie zarządzania kategoriami, w którym użytkownicy mogą rozbić wymiary na szczegóły, aby określić wymagania dotyczące dokonywania precyzyjniejszych rezerwacji.

#### <a name="example"></a>Przykład

W systemie jest skonfigurowana następująca hierarchia rezerwacji.

| Wymiar | Hierarchia |
|---|---|
| `ColorId` | 1 |
| `SizeId ` | 2 |
| `StyleId` | 3 |

Przyjmując tę hierarchię rezerwacji, można wykonać rezerwację w następujących porządkach wymiarów:

- `()`— nie jest podany wymiar.
- `(ColorId)`
- `(ColorId, SizeId)`
- `(ColorId, SizeId, StyleId)`

Porządek wymiarów musi ściśle naśladować sekwencję hierarchię rezerwacji, wymiar po wymiarze. Na przykład rezerwacje z sekwencją `(ColorId, StyleId)` nie będą dozwolone w tym przykładzie, ponieważ ta sekwencja nie jest zdefiniowana w hierarchii rezerwacji.

### <a name="control-feature-management"></a><a name="feature-switch"></a>Zarządzanie funkcjami sterowania

Dodatek Widoczność magazynu udostępnia funkcje, takie jak *OnHandReservation* i *OnHandMostSpecificBackgroundService*. Domyślnie te funkcje są wyłączone. Aby ich użyć, otwórz stronę **Konfiguracja** w Power Apps, a następnie włącz je na karcie **Zarządzanie funkcjami**.

### <a name="complete-and-update-the-configuration"></a>Kończenie i aktualizowanie konfiguracji

Po zakończeniu konfiguracji należy zatwierdzić wszystkie zmiany w aplikacji Widoczność magazynu. Aby zatwierdzić zmiany, wybierz pozycję **Aktualizuj konfigurację** w prawym górnym rogu strony **Konfiguracja** w Power Apps.

Po pierwszym wybraniu opcji **Aktualizuj konfigurację** system zażąda poświadczeń.

- **Identyfikator klienta** — identyfikator aplikacji systemu Azure utworzony dla aplikacji Widoczność magazynu.
- **Identyfikator dzierżawcy** — identyfikator dzierżawcy systemu Azure.
- **Klucz tajny klienta** — klucz tajny aplikacji systemu Azure utworzony dla aplikacji Widoczność magazynu.

Po zalogowaniu konfiguracja zostanie zaktualizowana w usłudze Widoczność magazynu.

> [!NOTE]
> Należy pamiętać o sprawdzeniu poprawności nazwy źródła danych, fizycznych miar i mapowań wymiarów przed zaktualizowaniem konfiguracji dla usługi Widoczność magazynu. Po wybraniu opcji **Aktualizuj konfigurację** nie będzie można zmodyfikować tych ustawień.

### <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>Znajdowanie punktu końcowego usługi

Jeśli nie znasz prawidłowego punktu końcowego usługi Widoczność magazynu, otwórz stronę **Konfiguracja** w programie Power Apps, a następnie wybierz pozycję **Pokaż punkt końcowy usługi** w prawym górnym rogu. Na stronie zostanie pokazany prawidłowy punkt końcowy usługi.

## <a name="operational-visibility"></a>Widoczność operacyjna

Strona **Widoczność operacyjna** zawiera wyniki zapytania o dostępne zapasy w czasie rzeczywistym oparte na różnych kombinacjach wymiarów. Po włączeniu funkcji *OnHandReservation* można również księgować żądania rezerwacji ze strony **Widoczność operacyjna**.

### <a name="on-hand-query"></a>Zapytanie o dostępne zapasy

Na karcie **Zapytanie o dostępne zapasy** są wyświetlane wyniki zapytania o dostępne zapasy w czasie rzeczywistym.

Po wybraniu karty **Zapytanie o dostępne zapasy** system żąda poświadczeń użytkownika, aby uzyskać token elementu nośnego wymagany do wykonywania zapytania w usłudze Widoczność magazynu. Token elementu nośnego można po prostu wkleić w polu **Token elementu nośnego** i zamknąć okno dialogowe. Następnie można zaksięgować żądanie zapytania o dostępne zapasy.

Jeśli token elementu nośnego jest nieprawidłowy lub wygasł, należy wkleić nowy w polu **Token elementu nośnego**. Wprowadź poprawne wartości w polach **Identyfikator klienta**, **Identyfikator dzierżawcy** i **Klucz tajny klienta**, a następnie wybierz opcję **Odśwież**. System automatycznie otrzyma nowy, prawidłowy token elementu nośnego.

Aby zaksięgować zapytanie o dostępne zapasy, wprowadź zapytanie w treści żądania. Użyj wzorca opisanego w temacie [Zapytanie przy użyciu metody księgowania](inventory-visibility-api.md#query-with-post-method).

![Ustawienia zapytania o dostępne zapasy](media/inventory-visibility-query-settings.png "Ustawienia zapytania o dostępne zapasy")

### <a name="reservation-posting"></a>Księgowanie rezerwacji

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Użyj karty **Księgowanie rezerwacji**, aby zaksięgować żądanie rezerwacji. Aby można było zaksięgować żądanie rezerwacji, należy włączyć funkcję *OnHandReservation*. Więcej informacji na temat tej funkcji zawiera temat [Rezerwacje dodatku Widoczność zapasów](inventory-visibility-reservations.md).

Aby zaksięgować żądanie rezerwacji, musisz wprowadzić wartość w treści żądania. Użyj wzorca opisanego w temacie [Tworzenie jednego zdarzenia rezerwacji](inventory-visibility-api.md#create-one-reservation-event). Następnie kliknij przycisk **Zaksięguj**. Aby wyświetlić szczegóły odpowiedzi na żądanie, wybierz opcję **Pokaż szczegóły**. Wartość **reservationId** można odczytać również ze szczegółów odpowiedzi.

## <a name="inventory-summary"></a>Podsumowanie zapasów

**Podsumowanie zapasów** jest dostosowanym widokiem *jednostki Suma dostępnych zapasów*. Zawiera podsumowanie zapasów dla produktów wraz ze wszystkimi wymiarami. Korzystając z **filtru zaawansowanego** z Dataverse, można utworzyć osobisty widok, który pokazuje ważne dla użytkownika wiersze. Zaawansowane opcje filtrowania pozwalają na tworzenie szerokiego zakresu widoków, od prostych do złożonych. Umożliwiają one również dodawanie grupowanych i zagnieżdżonych warunków do filtrów.

Aby dowiedzieć się więcej o używaniu **filtru zaawansowanego**, zobacz temat [Edytowanie lub tworzenie widoków osobistych przy użyciu zaawansowanych filtrów siatki](/powerapps/user/grid-filters-advanced)

W górnej części dostosowanego widoku są trzy pola: **Wymiar domyślny**, **Wymiar niestandardowy** i **Miara**. Za pomocą tych pól można kontrolować, które kolumny są widoczne.

Możesz wybrać nagłówek kolumny, aby filtrować lub sortować bieżący wynik.

W dolnej części niestandardowego widoku są wyświetlane informacje, jak „50 rekordów (wybrano 29)” lub „50 rekordów” Te informacje odnoszą się do aktualnie załadowanych rekordów z wyniku **filtru zaawansowanego**. Tekst „Wybrano 29” oznacza liczbę rekordów wybranych za pomocą filtru nagłówka kolumny dla ładowanych rekordów.

W dolnej części widoku znajduje się przycisk **Załaduj więcej**, który umożliwia załadowanie większej liczby rekordów z Dataverse. Domyślna liczba ładowanych rekordów wynosi 50. W przypadku wybrania opcji **Załaduj więcej** do widoku zostanie załadowanych następnych 1000 dostępnych rekordów. Liczba na przycisku **Załaduj więcej** wskazuje aktualnie załadowane rekordy oraz łączną liczbę rekordów dla wyniku **filtru zaawansowanego**.

![Podsumowanie zapasów](media/inventory-visibility-onhand-list.png "Podsumowanie zapasów")
