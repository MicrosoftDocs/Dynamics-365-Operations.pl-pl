---
title: Widoczność dostępnych zapasów — harmonogramy zmian i dostępność zapasów
description: W tym artykule opisano sposób planowania przyszłych zmian dostępnych towarów i obliczania ilości dostępnych towarów (ATP).
author: yufeihuang
ms.date: 05/11/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-04
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 4a0edeedfe42b43ef36c8ca091b01eef815f3632
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856201"
---
# <a name="inventory-visibility-on-hand-change-schedules-and-available-to-promise"></a>Widoczność dostępnych zapasów — harmonogramy zmian i dostępność zapasów

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób skonfigurowania funkcji *planowania zmian dostępnych towarów* w celu planowania przyszłych zmian dostępnych towarów i obliczania ilości dostępnych towarów (ATP). ATP to ilość towaru, która jest dostępna i którą można obiecać klientowi w następnym okresie. Użycie kalkulacji może znacznie zwiększyć twoje możliwości realizacji zamówień.

Dla wielu producentów, detalistów czy sprzedawców nie wystarczy wiedzieć, co jest aktualnie w magazynie. Muszą mieć pełny wgląd w przyszłą dostępność. Przyszła dostępność powinna uwzględniać przyszłą podaż, przyszły popyt i ATP.

## <a name="enable-and-set-up-the-features"></a><a name="setup"></a>Włączanie i konfigurowanie funkcji

Aby było można używać ATP, należy skonfigurować co najmniej jedną obliczoną miarę obliczania ilości ATP. Należy również włączyć tę funkcję i skonfigurować ustawienia ATP w programie Microsoft Power Apps.

### <a name="set-up-calculated-measures-for-atp-quantities"></a>Ustaw obliczone miary ilości ATP

Miara *obliczona ATP jest* wstępnie zdefiniowaną miarą obliczaną, która jest zwykle używana do znalezienia dostępnej ilości, która jest obecnie dostępna. Wielkość *podaży* jest sumą ilości dla tych środków fizycznych, które mają modyfikator typu *dodanie*, a *wielkość popytu* jest sumą ilości dla tych środków fizycznych, które mają modyfikator typu *odjęcie*.

Możesz dodać wiele działań obliczeniowych, aby obliczyć wiele ilości ATP. Jednakże całkowita liczba odrębnych środków fizycznych we wszystkich środkach obliczanych w ramach ATP powinna być mniejsza niż dziewięć.

> [!IMPORTANT]
> Obliczona miara jest złożeniem miar fizycznych. Jego formuła może zawierać tylko miary fizyczne bez duplikatów, a nie miary obliczone.

Na przykład konfigurujesz następującą miarę wyliczaną:

**On-hand-available** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*ReservPhysical* + *SoftReservePhysical* + *Outbound*)

Suma (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) reprezentuje podaż, a suma (*ReservPhysical* + *SoftReservePhysical* + *Outbound*) reprezentuje popyt. W związku z tym obliczoną miarę można zrozumieć w następujący sposób:

**On-hand-available** = *Supply* – *Demand*

Możesz dodać inną wyliczoną miarę, aby obliczyć **fizyczną ilość** ATP na rękę.

**Fizycznie dostępna ilość** = (*PhysicalInvent* + *OnHand* + *Unrestricted* + *QualityInspection* + *Inbound*) – (*Outbound*)

Istnieje osiem odrębnych miar fizycznych dla tych dwóch obliczonych miar ATP: *PhysicalInvent*, *OnHand*, *Unrestricted*, *QualityInspection*, *Inbound*, *ReservPhysical*, *SoftReservePhysical* i *Outbound*.

Aby uzyskać więcej informacji o miarach wyliczanych, zobacz: [Obliczone miary](inventory-visibility-configuration.md#calculated-measures).

### <a name="turn-on-the-on-hand-change-schedule-feature-and-configure-atp-settings"></a>Włącz funkcję harmonogramu zmian w czasie pracy i skonfiguruj ustawienia ATP

Wykonaj poniższe czynności, aby włączyć funkcję *Harmonogram zmian dostępnych na rękę* w Power Apps i skonfigurować ustawienia ATP.

1. Zaloguj się do Power Apps i otwórz dodatek Widoczność magazynu.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Zarządzanie funkcjami** włącz funkcję *OnhandChangeSchedule*.
1. Kliknij kartę **Ustawienia ATP**.
1. Kwerenda widoczności magazynu zapewni wynik, który zawiera każdą z obliczanych miar ATP, która jest dodawania w tym miejscu. Wybierz **przycisk Dodaj**, aby dodać nową miarę wyliczaną dla ATP.
1. Ustaw wartości w następujących polach:

    - **Źródło danych** – Wybierz źródło danych skojarzone z miarą wyliczaną.
    - **Miara obliczona** — umożliwia wybór miary obliczanej skojarzonej z wybranym źródłem danych i służącej do znalezienia dostępnej ilości.
    - **Zaplanuj okres** — umożliwia wprowadzenie liczby dni, przez które użytkownicy mogą wyświetlać i przesyłać zaplanowane zmiany ilości w ramach zaplanowanego okresu, gdy jest używana wybrana miara obliczona. Użytkownicy, którzy zawierają kwerendy dotyczące informacji o zapasach, otrzymają informacje na temat ilości w magazynie, zaplanowanych zmian zapasów oraz ilości ATP dla każdego dnia w tym okresie, począwszy od bieżącej daty. Wybierz liczbę całkowitą z liczby 1 do 7.

    > [!IMPORTANT]
    > Okres harmonogramu zawiera bieżącą datę. Dzięki temu użytkownicy mogą planować zmiany w stanie, tak aby zostały wprowadzone w dowolnym czasie od daty bieżącej (dzień, w którym zmiana jest przesłana) do dnia (okres planowania – 1) dnia w przyszłości.

1. Wybierz opcję **Zapisz**.
1. Powtarzaj kroki od 5 do 7, aż dodasz wszystkie miary obliczeniowe wymagane dla ATP.
1. Po zakończeniu konfigurowania wszystkich wymaganych ustawień wybierz opcję **Aktualizuj konfigurację**.

Aby uzyskać więcej informacji, zobacz temat [Uzupełnij i zaktualizuj konfigurację](inventory-visibility-configuration.md).

## <a name="how-the-on-hand-change-schedule-and-atp-calculations-work"></a>Jak działa harmonogram podręcznych zmian i obliczenia ATP

Harmonogram *zmian w ilości określa* oczekiwane daty i ilości zaplanowanych zmian w dostępnej ilości. Możesz przesłać harmonogram zmian na bieżąco do funkcji Widoczność zasobów reklamowych, pod warunkiem, że daty mieszczą się w okresie zdefiniowanym w ustawieniu **Zaplanuj okres** (zobacz [Włącz i skonfiguruj funkcje](#setup) Sekcja). Użytkownicy, którzy zawierają kwerendy dotyczące informacji o zapasach, otrzymają informacje na temat ilości w magazynie, zaplanowanych zmian zapasów oraz ilości ATP dla każdego dnia w tym okresie.

Zaplanowane zmiany są początkowo niezatwierdzone, dlatego nie mają wpływu na rzeczywiste dostępne ilości w systemie. Aby zatwierdzić zmiany, należy przesłać *zdarzenie zmiany dostępnych zapasów,* które aktualizuje faktycznie dostępną ilość. Następnie należy przywrócić zaplanowaną zmianę, przesyłając harmonogram zmian zapasów dla pasującej ilości ujemnej.

Można na przykład umieścić zamówienie na 10 osób, które ma być przyjeżdżać jutro. W związku z tym przesyłasz dostępny harmonogram zmian, który ma przychodzącą ilość 10 i jest datowany na jutro. Gdy zamówienie przybędzie następnego dnia, należy dodać zlecenie do fizycznie dostępnych zapasów. Następnie należy zatwierdzić zmianę w systemie, aby zaktualizować rzeczywistą ilość w zapasach. Aby zatwierdzić zmianę, należy przesłać zdarzenie zmiany ilości przychodzącej 10. Następnie cofasz zaplanowaną zmianę, przesyłając harmonogram dostępnych zmian, który ma przychodzącą ilość -10.

Kwerenda widoczności zapasów w odniesieniu do ilości dostępnych zapasów i ATP zwraca następujące informacje dla każdego dnia w okresie harmonogramu:

- **Data** – Służy do wprowadzania ostatniej daty, do których odnosi się wiersz daty. Strefą czasową jest uniwersalny czas koordynowany (UTC).
- **Ilość dostępna —** rzeczywista ilość dostępna w określonym dniu Obliczenia są dokonywane zgodnie z obliczoną miarą ATP skonfigurowaną dla widoczności zapasów.
- **Zaplanowane dostawy** — suma wszystkich zaplanowanych ilości przychodzących, które w określonym dniu nie stały się fizycznie dostępne do natychmiastowego zużycia lub wysyłki.
- **Zaplanowany popyt** — suma wszystkich zaplanowanych ilości wychodzących, które nie zostały zużyte lub wysłane w określonym dniu
- **Ilość ATP** — Minimalna prognozowana ilość dostępnych zapasów, która jest dostępna od określonej daty do końca okresu harmonogramu. Ta ilość obejmuje wszystkie zaplanowane korekty ilości. Jest to maksymalna ilość, jaka może zostać obiecana w bieżącym dniu jako ilość dostawy lub zużycia tego dnia.

Na przykład, jeśli bieżąca data to 1 lutego 2022 r., a okres harmonogramu to 7, użytkownicy mogą przesłać zaplanowane zmiany w stanie, które mają wystąpić od 1 do 7 lutego 2022. W takim przypadku ilość ATP na przykład dla 3 lutego jest obliczana na podstawie dostępnej ilości dla tego dnia oraz zaplanowanych ilości od 3 lutego do 7 lutego.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak seria zaplanowanych zmian ilości wpływa na ilości dostępne i ATP raportowane w raporcie Widoczność zapasów. Pokazano w nim także sposób zatwierdzania zaplanowanej zmiany, wpływ zatwierdzonej zmiany harmonogramu na wyniki oraz na to, co może wystąpić, jeśli nie zostanie ona zaplanowana.

W wynikach w tym przykładzie jest pokazywana *prognozowana wartość w ramach* projektu. Ta wartość uwzględnia wszystkie zaplanowane aktualizacje dla celów ilustracji, ale nie jest w rzeczywistości raportowa podczas wykonywania kwerendy Widoczność zapasów.

1. Następujące ustawienia są konfigurowane dla systemu na stronie **ustawień ATP** w Power Apps:

    - **Miara obliczona ATP** — Masz miarę wyliczaną o nazwie *Dostępne zapasy*. Jest obliczana jako ilość *Dostępne zapasy = podaż – popyt*. Tę miarę wybiera się w tym miejscu.
    - **Okres harmonogramu** — należy wybrać *7*.

1. Należy uwzględnić też następujące warunki:

    - Obecna data to 1 lutego 2022 r.
    - Obecna ilość w kasie to 20.

1. Dla daty bieżącej (1 lutego 2022) do widoczności zapasów przesyłasz zaplanowaną ilość zapotrzebowania 3. W związku z tym przewidywana dostępna ilość wynosi 17. Poniższa tabela przedstawia wynik.

    | Data | Dostępne zapasy | Planowana dostawa | Zaplanowany popyt | Prognozowane są informacje o zdjętowanych ramach | Dostępność zapasów |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | | | 17 | 17 |
    | 2022-02-04 | 20 | | | 17 | 17 |
    | 2022-02-05 | 20 | | | 17 | 17 |
    | 2022-02-06 | 20 | | | 17 | 17 |
    | 2022-02-07 | 20 | | | 17 | 17 |

1. W dniu bieżącym (1 lutego 2022) przesyłasz zaplanowaną ilość dostaw 10 na 3 lutego 2022. Poniższa tabela przedstawia wynik.

    | Data | Dostępne zapasy | Planowana dostawa | Zaplanowany popyt | Prognozowane są informacje o zdjętowanych ramach | Dostępność zapasów |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 17 |
    | 2022-02-02 | 20 | | | 17 | 17 |
    | 2022-02-03 | 20 | 10 | | 27 | 27 |
    | 2022-02-04 | 20 | | | 27 | 27 |
    | 2022-02-05 | 20 | | | 27 | 27 |
    | 2022-02-06 | 20 | | | 27 | 27 |
    | 2022-02-07 | 20 | | | 27 | 27 |

1. W dniu bieżącym (1 lutego 2022) można przesłać następujące zaplanowane zmiany ilości:

    - Ilość zapotrzebowania 15 na 4 lutego 2022
    - Ilość dostaw 1 na dzień 5 lutego 2022 r.
    - Ilość dostaw 3 na dzień 6 lutego 2022 r.

    Poniższa tabela przedstawia wynik.

    | Data | Dostępne zapasy | Planowana dostawa | Zaplanowany popyt | Prognozowane są informacje o zdjętowanych ramach | Dostępność zapasów |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 20 | | 3 | 17 | 12 |
    | 2022-02-02 | 20 | | | 17 | 12 |
    | 2022-02-03 | 20 | 10 | | 27 | 12 |
    | 2022-02-04 | 20 | | 15 | 12 | 12 |
    | 2022-02-05 | 20 | 1 | | 13 | 13 |
    | 2022-02-06 | 20 | 3 | | 16 | 16 |
    | 2022-02-07 | 20 | | | 16 | 16 |

1. W dniu bieżącym (1 lutego 2022 r.) wysyłasz zaplanowaną ilość zapotrzebowania wynoszącą 3. W związku z tym należy zatwierdzić tę zmianę, aby była ona odzwierciedlona w rzeczywistej ilości w zapasach. Aby zatwierdzić zmianę, należy przesłać zdarzenie zmiany ilości wychodzącej 3. Następnie cofasz zaplanowaną zmianę, przesyłając harmonogram dostępnych zmian, który ma wychodzącą ilość -3. Poniższa tabela przedstawia wynik.

    | Data | Dostępne zapasy | Planowana dostawa | Zaplanowany popyt | Prognozowane są informacje o zdjętowanych ramach | Dostępność zapasów |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-01 | 17 | | 0 | 17 | 12 |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |

1. Następnego dnia (2 lutego 2022) okres harmonogramu zmienia się w przód o jeden dzień. Poniższa tabela przedstawia wynik.

    | Data | Dostępne zapasy | Planowana dostawa | Zaplanowany popyt | Prognozowane są informacje o zdjętowanych ramach | Dostępność zapasów |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-02 | 17 | | | 17 | 12 |
    | 2022-02-03 | 17 | 10 | | 27 | 12 |
    | 2022-02-04 | 17 | | 15 | 12 | 12 |
    | 2022-02-05 | 17 | 1 | | 13 | 13 |
    | 2022-02-06 | 17 | 3 | | 16 | 16 |
    | 2022-02-07 | 17 | | | 16 | 16 |
    | 2022-02-08 | 17 | | | 16 | 16 |

1. Jednak dwa dni później (4 lutego 2022) ilość dostawy 10 zaplanowana na 3 lutego wciąż nie nadeszła. Poniższa tabela przedstawia wynik.

    | Data | Dostępne zapasy | Planowana dostawa | Zaplanowany popyt | Prognozowane są informacje o zdjętowanych ramach | Dostępność zapasów |
    | --- | --- | --- | --- | --- | --- |
    | 2022-02-04 | 17 | | 15 | 2 | 2 |
    | 2022-02-05 | 17 | 1 | | 3 | 3 |
    | 2022-02-06 | 17 | 3 | | 6 | 6 |
    | 2022-02-07 | 17 | | | 6 | 6 |
    | 2022-02-08 | 17 | | | 6 | 6 |
    | 2022-02-09 | 17 | | | 6 | 6 |
    | 2022-02-10 | 17 | | | 6 | 6 |

    Jak widać planowane (ale nie zatwierdzone) zmiany w stanie zapasów nie wpływają na rzeczywistą ilość w zapasach.

## <a name="submit-change-schedules-change-events-and-atp-queries-through-the-api"></a><a name="api-urls"></a>Przesyłanie harmonogramów zmian, zdarzeń zmian i kwerend ATP za pomocą interfejsu API

Poniższych adresów URL interfejsu programowania aplikacji (API) można używać do przesyłania harmonogramów zmian w stanie, zmieniania zdarzeń i kwerend.

| Ścieżka | Metoda | Opis |
| --- | --- | --- |
| `/api/environment/{environmentId}/onhand/changeschedule` | `POST` | Utwórz jedną zaplanowaną zmianę od ręki. |
| `/api/environment/{environmentId}/onhand/changeschedule/bulk` | `POST` | Utwórz wiele zaplanowanych zmian od ręki. |
| `/api/environment/{environmentId}/onhand` | `POST` | Tworzenie jednego zdarzenia zmiany dostępnych zapasów. |
| `/api/environment/{environmentId}/onhand/bulk` | `POST` | Tworzenie wielu zdarzeń zmiany. |
| `/api/environment/{environmentId}/onhand/indexquery` | `POST` | Zapytanie przy użyciu metody `POST`. |
| `/api/environment/{environmentId}/onhand` | `GET` | Zapytanie przy użyciu metody `GET`. |

Więcej informacji zawiera temat [Publiczne interfejsy API widoczności zasobów reklamowych](inventory-visibility-api.md).

### <a name="create-one-on-hand-change-schedule"></a>Utwórz jeden harmonogram zmian zapasów dostępnych od ręki

Harmonogram zmian na miejscu jest tworzony przez wysłanie żądania `POST` do odpowiedniego adresu URL usługi Widoczność zapasów (zobacz sekcję [Wysyłanie harmonogramów zmian, zdarzeń zmian i zapytań ATP przez sekcję interfejsu API](#api-urls)). Możesz również przesłać żądania zbiorcze.

Harmonogram zmian zapasów dostępnych od ręki może być utworzony tylko wtedy, gdy planowana data jest pomiędzy datą bieżącą a końcem bieżącego okresu harmonogramu. Format daty powinien być następujący: *rok-miesiąc-dzień* (np. **2022-02-01**). Format czasu musi być dokładny tylko do jednego dnia.

Ten interfejs API tworzy pojedynczy harmonogram zmian w miejscu pracy.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        id: string,
        organizationId: string,
        productId: string,
        dimensionDataSource: string, # optional
        dimensions: {
            [key:string]: string,
        },
        quantitiesByDate: {
            [datetime:datetime]: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
        },
    }
```

W poniższym przykładzie pokazano zawartość przykładowej treści bez `dimensionDataSource`.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    },
    "quantitiesByDate":
    {
        "2022-02-01": // today
        {
            "pos":{
                "inbound": 10
            }
        }
    }
}
```

### <a name="create-multiple-on-hand-change-schedules"></a>Tworzenie wielu harmonogramów zmian w stanie gotowości do pracy

Ten interfejs API może tworzyć wiele rekordów jednocześnie. Jedyną różnicą między tym interfejsem API a interfejsem API jednego zdarzenia są wartości `Path` i `Body`. W tym interfejsie API `Body` dostarcza tablicę rekordów. Maksymalna dozwolona liczba rekordów wynosi 512. Dlatego interfejs API zbiorczego harmonogramu zmian może obsługiwać jednocześnie do 512 zaplanowanych zmian.

```txt
Path:
    /api/environment/{environmentId}/onhand/changeschedule/bulk
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    [
        {
            id: string,
            organizationId: string,
            productId: string,
            dimensionDataSource: string,
            dimensions: {
                [key:string]: string,
            },
            quantityDataSource: string, # optional
            quantitiesByDate: {
                [datetime:datetime]: {
                    [dataSourceName:string]: {
                        [key:string]: number,
                    },
                },
            },
        },
        ...
    ]
```

W poniższym przykładzie pokazano zawartość przykładowej treści.

```json
[
    {
        "id": "id-bike-0001",
        "organizationId": "usmf",
        "productId": "Bike",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-01": // today
            {
                "pos":{
                    "inbound": 10
                }
            }
        }
    },
    {
        "id": "id-car-0002",
        "organizationId": "usmf",
        "productId": "Car",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red",
            "SizeId&quot;: &quot;Small"
        },
        "quantitiesByDate":
        {
            "2022-02-05":
            {
                "pos":{
                    "outbound": 10
                }
            }
        }
    }
]
```

### <a name="create-on-hand-change-events"></a>Tworzenie zdarzeń zmiany dostępnych zapasów

Harmonogramy wydarzeń na bieżąco są tworzone przez przesłanie żądania `POST` do odpowiedniego adresu URL usługi Inventory Visibility (patrz sekcja [Przesyłanie harmonogramów zmian, zdarzeń zmian i zapytań ATP za pośrednictwem interfejsu API](#api-urls)). Możesz również przesłać żądania zbiorcze.

> [!NOTE]
> Zdarzenia zmiany dostępnych zapasów nie są unikatowe dla funkcji ATP, ale są częścią standardowego interfejsu API widoczności zapasów. Ten przykład został uwzględniony, ponieważ zdarzenia są istotne podczas pracy z ATP. Zdarzenia zmian na rękę przypominają rezerwacje zmian na rękę, ale komunikaty o zdarzeniach muszą być wysyłane do innego adresu URL interfejsu API, a zdarzenia używają `quantities` zamiast `quantityByDate` w treści wiadomości. Aby uzyskać więcej informacji o zdarzeniach zmian dostępnych zapasów i innych funkcjach interfejsu API widoczności zapasów, zobacz interfejsy [API dotyczące widoczności zapasów](inventory-visibility-api.md#create-one-onhand-change-event).

Poniższy przykład przedstawia treść żądania, która zawiera pojedyncze zdarzenie zmiany dostępnej.

```json
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "SizeId": "Big",
        "ColorId": "Red"
    },
    "quantities": {
        "pos": {
            "inbound": 10.0
        }
    }
}
```

## <a name="query-the-scheduled-on-hand-changes-and-atp-results"></a>Wykonywanie kwerendy dotyczącej zaplanowanych zmian i wyników ATP

Możesz wysyłać zapytania do zaplanowanych bieżących zmian i wyników ATP, przesyłając żądanie `POST` lub `GET` do odpowiedniego adresu URL interfejsu API (patrz [Przesyłanie harmonogramów zmian, zdarzeń zmian i zapytań ATP za pośrednictwem interfejsu API](#api-urls) sekcji).

W żądaniu ustaw `QueryATP` na *prawda*, jeśli chcesz odpytywać zaplanowane bieżące zmiany i wyniki ATP.

- Jeśli przesyłasz żądanie za pomocą metody `GET`, ustaw ten parametr w adresie URL.
- Jeśli przesyłasz żądanie za pomocą metody `POST`, ustaw ten parametr w treści żądania.

> [!NOTE]
> Niezależnie od tego, czy parametr `returnNegative` jest ustawiony na *prawda* lub *fałsz* w treści żądania, wynik będzie zawierał wartości ujemne w przypadku zapytania dotyczącego zaplanowanych dostępnych zmian i wyników ATP. Te ujemne wartości zostaną uwzględnione, ponieważ jeśli zaplanowano tylko zamówienia popytowe lub ilości dostaw są mniejsze niż ilości popytu, ilości planowanych zmian w zapasach będą ujemne. Jeśli wartości ujemne nie zostały uwzględnione, wyniki byłyby mylące. Aby uzyskać więcej informacji dotyczących tej opcji i sposobu działania tej opcji w przypadku innych typów kwerend, zobacz [interfejsy API publiczne widoczności zapasów](inventory-visibility-api.md#query-with-post-method).

```txt
Path:
    /api/environment/{environmentId}/onhand/indexquery
Method:
    Post
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Body:
    {
        dimensionDataSource: string, # Optional
        filters: {
            organizationId: string[],
            productId: string[],
            siteId: string[],
            locationId: string[],
            [dimensionKey:string]: string[],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

W poniższym przykładzie pokazano, jak utworzyć treść żądania, która może zostać przesłana do widoczności zapasów za pomocą metody `POST`.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["Bike"],
        "siteId": ["1"],
        "LocationId": ["11"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true,
    "QueryATP":true
}
```

### <a name="get-method-example"></a>Przykład metody GET

```txt
Path:
    /api/environment/{environmentId}/onhand
Method:
    Get
Headers:
    Api-Version="1.0"
    Authorization="Bearer $access_token"
ContentType:
    application/json
Query(Url Parameters):
    groupBy
    returnNegative
    [Filters]
```

W poniższym przykładzie pokazano, jak utworzyć adres URL żądania jako żądanie `GET`.

```txt
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand?organizationId=usmf&productId=Bike&SiteId=1&LocationId=11&groupBy=ColorId,SizeId&returnNegative=true&QueryATP=true
```

Wynik tego żądania `GET` jest dokładnie taki sam, jak wynik żądania `POST` w poprzednim przykładzie.

### <a name="query-result-example"></a>Przykład wyniku zapytania

Obie poprzednie przykłady kwerend mogą powodować następującą odpowiedź. W tym przykładzie system jest skonfigurowany przy użyciu następujących ustawień:

- **Miara obliczona ATP:** *iv.onhand = pos.inbound – pos.outbound*
- **Okres planowania:** *7*

Oto przykład treści odpowiedzi.

```json
[
    {
        "quantitiesByDate": {
            "2022-02-02T00:00:00": {
                "pos": {
                    "outbound": 5,
                    "inbound": 0,
                },
                "iv": {
                    "onhand": -5,
                },
            },
            "2022-02-06T00:00:00": {
                "pos": {
                    "inbound": 7,
                    "outbound": 0,
                },
                "iv": {
                    "onhand": 7,
                },
            }
        },
        "atpQuantities": {
            "2022-02-01T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-02T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-03T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-04T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-05T00:00:00Z": {
                "iv": {
                    "onhand": 5.0
                }
            },
            "2022-02-06T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            },
            "2022-02-07T00:00:00Z": {
                "iv": {
                    "onhand": 12.0
                }
            }
        },
        "productId": "Bike ",
        "dimensions": {
            "ColorId": "Red",
            "SizeId": "Big",
            "siteid": "1",
            "locationid": "11"
        },
        "quantities": {
            "pos": {
                "inbound": 10.0,
                "outbound": 0,
            },
            "iv": {
                "onhand": 10.0,
            }
        }
    }
]
```
