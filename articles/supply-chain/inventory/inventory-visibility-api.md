---
title: Publiczne interfejsy API dodatku Widoczność magazynu
description: W tym artykule opisano publiczne interfejsy API udostępniane przez dodatek Widoczność magazynu.
author: yufeihuang
ms.date: 12/09/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 82a43954db8b10554c449f3e8d32ba7e5d7c7f27
ms.sourcegitcommit: ce58bb883cd1b54026cbb9928f86cb2fee89f43d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2022
ms.locfileid: "9719356"
---
# <a name="inventory-visibility-public-apis"></a>Publiczne interfejsy API dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]


W tym artykule opisano publiczne interfejsy API udostępniane przez dodatek Widoczność magazynu.

Publiczny interfejs API REST w dodatku Widoczność magazynu przedstawia kilka konkretnych punktów końcowych integracji. Obsługuje on cztery główne typy interakcji:

- Księgowanie dostępnych zmian zapasów w dodatku z systemu zewnętrznego
- Konfigurowanie lub zastępowanie ilości dostępnych zapasów w dodatku z zewnętrznego systemu
- Księgowanie zdarzeń rezerwacji w dodatku z systemu zewnętrznego
- Badanie bieżących ilości dostępnych zapasów z systemu zewnętrznego

W poniższej tabeli przedstawiono obecnie dostępne interfejsy API:

| Ścieżka | Metoda | opis |
|---|---|---|
| /api/environment/{environmentId}/onhand | Księguj | [Tworzenie jednego zdarzenia zmiany dostępnych zapasów](#create-one-onhand-change-event) |
| /api/environment/{environmentId}/onhand/bulk | Księguj | [Tworzenie wielu zdarzeń zmiany](#create-multiple-onhand-change-events) |
| /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk | Księguj | [Ustawianie/zastępowanie dostępnych ilości](#set-onhand-quantities) |
| /api/environment/{environmentId}/onhand/reserve | Księguj | [Tworzenie jednego zdarzenia rezerwacji](#create-one-reservation-event) |
| /api/environment/{environmentId}/onhand/reserve/bulk | Księguj | [Tworzenie wielu zdarzeń rezerwacji](#create-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/unreserve | Księguj | [Wycofanie jednego zdarzenia rezerwacji](#reverse-one-reservation-event) |
| /api/environment/{environmentId}/onhand/unreserve/bulk | Księguj | [Wycofanie wielu zdarzeń rezerwacji](#reverse-multiple-reservation-events) |
| /api/environment/{environmentId}/onhand/changeschedule | Księguj | [Utwórz jedną zaplanowaną zmianę od ręki](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/changeschedule/bulk | Księguj | [Utwórz wiele zaplanowanych zmian od ręki](inventory-visibility-available-to-promise.md) |
| /api/environment/{environmentId}/onhand/indexquery | Księguj | [Zapytanie przy użyciu metody POST](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Pobierz | [Zapytanie przy użyciu metody GET](#query-with-get-method) |
| /api/environment/{environmentId}/onhand/exactquery | Księguj | [Dokładne zapytanie przy użyciu metody POST](#exact-query-with-post-method) |
| /api/environment/{environmentId}/allocation/allocate | Księguj | [Utwórz jedno zdarzenie przydziału](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/unallocate | Księguj | [Utwórz jedno zdarzenie cofnięcia przydziału](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/reallocate | Księguj | [Utwórz jedno zdarzenie ponownego przydziału](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/consume | Księguj | [Tworzenie jednego zdarzenia zużycia](inventory-visibility-allocation.md#using-allocation-api) |
| /api/environment/{environmentId}/allocation/query | Księguj | [Wynik alokacji zapytań](inventory-visibility-allocation.md#using-allocation-api) |

> [!NOTE]
> Część {environmentId} ścieżki jest identyfikatorem środowiska w usługach Microsoft Dynamics Lifecycle Services (LCS).
> 
> API zbiorcze może zwrócić maksymalnie 512 rekordów dla każdego żądania.

Firma Microsoft dostarcza kolekcję gotowych do użycia żądań *Postman*. Kolekcję można zaimportować do oprogramowania *Postman*, korzystając z następującego udostępnionego łącza: <https://www.getpostman.com/collections/95a57891aff1c5f2a7c2>

## <a name="find-the-endpoint-according-to-your-lifecycle-services-environment"></a>Znajdowanie punktu końcowego zgodnie ze środowiskiem Lifecycle Services.

Mikrousługa Widoczność magazynu jest wdrażana w Microsoft Azure Service Fabric w wielu lokalizacjach geograficznych i wielu regionach. Obecnie nie istnieje centralny punkt końcowy, który może automatycznie przekierować żądanie do odpowiedniej lokalizacji geograficznej i regionu. W związku z tym należy skomponować fragmenty informacji w adresie URL, stosując następujący wzorzec:

`https://inventoryservice.<RegionShortName>-il<IsLandNumber>.gateway.prod.island.powerapps.com`

Krótka nazwa regionu znajduje się w środowisku Microsoft Dynamics Lifecycle Services (LCS). W poniższej tabeli przedstawiono obecnie dostępne regiony.

| Region systemu Azure        | Krótka nazwa regionu |
| ------------------- | ----------------- |
| Australia Wschodnia      | eau               |
| Australia Południowo-Wschodnia | seau              |
| Kanada środkowa      | cca               |
| Kanada wschodnia         | eca               |
| Europa Północna        | neu               |
| Europa Zachodnia         | weu               |
| Wschodnie stany USA             | eus               |
| Zachodnie stany USA             | wus               |
| Południowe Zjednoczone Królestwo            | suk               |
| Zachodnie Zjednoczone Królestwo             | wuk               |
| Japonia Wschodnia          | ejp               |
| Japonia Zachodnia          | wjp               |
| Brazylia Południowa        | sbr               |
| Południowo-środkowe stany USA    | scus              |

Numer wyspy wskazuje miejsce wdrażania środowiska LCS w Service Fabric. Obecnie nie można pobrać tych informacji ze strony użytkownika.

Firma Microsoft wbudowała interfejs użytkownika (UI) w Power Apps, dzięki czemu można uzyskać pełny punkt końcowy mikrousługi. Więcej informacji można znaleźć w temacie [Znajdowanie punktu końcowego usługi](inventory-visibility-configuration.md#get-service-endpoint).

## <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Uwierzytelnianie

Token zabezpieczeń platformy służy do wywołania publicznego interfejsu API Widoczność magazynu. Dlatego należy wygenerować token _Azure Active Directory (Azure AD)_ przy użyciu aplikacji Azure AD. Następnie należy użyć tokenu Azure AD, aby uzyskać _token dostępu_ z usługi zabezpieczeń.

Firma Microsoft dostarcza kolekcję gotowych do pobierania tokenów *Postman*. Kolekcję można zaimportować do oprogramowania *Postman*, korzystając z następującego udostępnionego łącza: <https://www.getpostman.com/collections/496645018f96b3f0455e>

Procedura uzyskiwania tokenu usługi zabezpieczeń jest następująca.

1. Zaloguj się do portalu Azure i użyj go, aby znaleźć wartości `clientId` i `clientSecret` dla swojej aplikacji Dynamics 365 Supply Chain Management.
1. Pobierz token usługi Azure AD (`aadToken`), przesyłając żądanie HTTP z następującymi właściwościami:

   - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/v2.0/token`
   - **Metoda:** `GET`
   - **Treść (dane formularza):**

     | Klucz           | Wartość                                            |
     | ------------- | -------------------------------------------------|
     | client_id     | ${aadAppId}                                      |
     | client_secret | ${aadAppSecret}                                  |
     | grant_type    | client_credentials                               |
     | zakres         | 0cdb527f-a8d1-4bf8-9436-b352c68682b2/.domyślne    |

   Odpowiedź powinna zawierać token Azure AD (`aadToken`). Powinna ona przypominać następujący przykład.

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "access_token": "eyJ0eX...8WQ"
   }
   ```

1. Sformułuj żądanie JavaScript Object Notation (JSON) przypominające następujący przykład.

   ```json
   {
       "grant_type": "client_credentials",
       "client_assertion_type": "aad_app",
       "client_assertion": "{Your_AADToken}",
       "scope": "https://inventoryservice.operations365.dynamics.com/.default",
       "context": "{$LCS_environment_id}",
       "context_type": "finops-env"
   }
   ```

   Należy uwzględnić następujące informacje:

   - Wartość `client_assertion` musi być tokenem Azure AD (`aadToken`) otrzymanym w poprzednim kroku.
   - Wartość `context` musi być identyfikatorem środowiska LCS, w którym ma zostać wdrożony dodatek.
   - Ustaw wszystkie inne wartości, tak jak pokazano w przykładzie.

1. Pobierz token usługi (`access_token`), przesyłając żądanie HTTP z następującymi właściwościami:

   - **URL:** `https://securityservice.operations365.dynamics.com/token`
   - **Metoda:** `POST`
   - **Nagłówek HTTP:** zawiera wersję API. (Klucz to `Api-Version`, a wartość to `1.0`.)
   - **Treść:** umożliwia dołączenie żądania JSON utworzonego w poprzednim kroku.

   Odpowiedź powinna zawierać token dostępu (`access_token`). Musisz użyć tego tokenu do wywołania interfejsu API Widoczność magazynu. Oto przykład.

   ```json
   {
       "access_token": "{Returned_Token}",
       "token_type": "bearer",
       "expires_in": 3600
   }
   ```

> [!IMPORTANT]
> Gdy do wywołania interfejsów API publicznych widoczności zapasów jest używać kolekcji żądań *Postman*, należy dla każdego żądania dodać token okaziciela. Aby znaleźć token okaziciela, wybierz kartę **Autoryzacja** pod adresem URL żądania, wybierz typ **tokenu okaziciela** i skopiuj token dostępu, który został pobrany w ostatnim kroku. W dalszych częściach tego artykułu, `$access_token` będzie używany do reprezentowania tokena, który został pobrany w ostatnim kroku.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Tworzenie zdarzeń zmiany dostępnych zapasów

Istnieją dwa interfejsy API do tworzenia zdarzeń zmiany dostępnych zapasów:

- Tworzenie jednego rekordu: `/api/environment/{environmentId}/onhand`
- Tworzenie wielu rekordów: `/api/environment/{environmentId}/onhand/bulk`

W poniższej tabeli podsumowano znaczenie poszczególnych pól w treści JSON.

| Identyfikator pola | Opis |
|---|---|
| `id` | Unikatowy identyfikator określonego zdarzenia zmiany. Jeśli komunikacja z usługą nie powiedzie się w trakcie księgowania, ten identyfikator służy do zapewnienia, że to samo zdarzenie nie zostanie zliczone dwukrotnie w systemie. |
| `organizationId` | Identyfikator organizacji połączonej ze zdarzeniem. Wartość jest mapowana na identyfikator organizacji lub obszaru danych w Supply Chain Management. |
| `productId` | Identyfikator produktu. |
| `quantities` | Ilość, o którą musi zostać zmieniona dostępna ilość. Jeśli na przykład na półce zostanie dołożonych 10 nowych książek, ta wartość będzie wynosić `quantities:{ shelf:{ received: 10 }}`. Jeśli trzy książki zostaną usunięte z półki lub sprzedane, ta wartość będzie wynosić `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | Źródło danych wymiarów używanych w zdarzeniu zmiany księgowania i zapytaniu. W przypadku określenia źródła danych można wykorzystać niestandardowe wymiary z określonego źródła danych. Dodatek Widoczność magazynu może używać konfiguracji wymiarów do mapowania niestandardowych wymiarów na ogólne wymiary domyślne. Jeśli nie określiło wartości `dimensionDataSource`, w zapytaniach można stosować tylko ogólne [wymiary podstawowe](inventory-visibility-configuration.md#data-source-configuration-dimension). |
| `dimensions` | Dynamiczna para klucz-wartość. Te wartości są mapowane na niektóre wymiary w Supply Chain Management. Można jednak dodać również wymiary niestandardowe (na przykład _Źródło_), aby wskazać, czy zdarzenie pochodzi z Supply Chain Management, czy z systemu zewnętrznego. |

> [!NOTE]
> Parametry `siteId` i `locationId` konstruują [konfigurację partycji](inventory-visibility-configuration.md#partition-configuration). Należy je zatem określić w wymiarach podczas tworzenia zdarzeń zmiany dostępnego czasu, określania lub zastępowania ilości w dostępnej ilości albo tworzenia zdarzeń rezerwacji.

### <a name="create-one-on-hand-change-event"></a><a name="create-one-onhand-change-event"></a>Tworzenie jednego zdarzenia zmiany dostępnych zapasów

Ten interfejs API tworzy jedno zdarzenie zmiany dostępnych zapasów.

```txt
Path:
    /api/environment/{environmentId}/onhand
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
        dimensionDataSource: string, # Optional
        dimensions: {
            [key:string]: string,
        },
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
    }
```

W poniższym przykładzie pokazano zawartość przykładowej treści. W tym przykładzie użytkownik księguje zdarzenie zmiany dotyczące produktu *T-shirt*. To zdarzenie pochodzi z punkt sprzedaży (POS), a odbiorca zwrócił do sklepu czerwony T-shirt. To zdarzenie spowoduje zwiększenie ilości produktu *T-shirt* o 1.

```json
{
    "id": "123456",
    "organizationId": "SCM_IV",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "posMachineId": "0001",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

W poniższym przykładzie pokazano zawartość przykładowej treści bez `dimensionDataSource`. W takim przypadku element `dimensions` będzie [wymiarami bazowymi](inventory-visibility-configuration.md#data-source-configuration-dimension). Jeśli `dimensionDataSource` jest ustawiony, `dimensions` mogą być wymiarami źródłowymi danych lub wymiarami bazowymi.

```json
{
    "id": "123456",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red"
    },
    "quantities": {
        "pos": {
            "inbound": 1
        }
    }
}
```

### <a name="create-multiple-change-events"></a><a name="create-multiple-onhand-change-events"></a>Tworzenie wielu zdarzeń zmiany

Ten interfejs API może tworzyć wiele rekordów jednocześnie. Jedyną różnicą między tym interfejsem API a [interfejsem API jednego zdarzenia](#create-one-onhand-change-event) są wartości `Path` i `Body`. W tym interfejsie API `Body` dostarcza tablicę rekordów. Maksymalna liczba rekordów wynosi 512, co oznacza, że interfejs API do masowych zmian w podręczniku może obsługiwać do 512 zdarzeń zmiany jednocześnie.

```txt
Path:
    /api/environment/{environmentId}/onhand/bulk
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
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
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
        "id": "123456",
        "organizationId": "SCM_IV",
        "productId": "iv_postman_product_1",
        "dimensionDataSource": "pos",
        "dimensions": {
            "posSiteId": "posSite1",
            "posLocationId": "posLocation1",
            "posMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "SCM_IV",
        "productId": "iv_postman_product_2",
        "dimensions": {
            "siteId": "iv_postman_site",
            "locationId": "iv_postman_location",
            "colorId&quot;: &quot;black"
        },
        "quantities": {
            "pos": { "outbound": 3 }
        }
    }
]
```

## <a name="setoverride-on-hand-quantities"></a><a name="set-onhand-quantities"></a>Ustawianie/zastępowanie dostępnych ilości

Interfejs _Ustaw dostępną ilość_ umożliwia zastąpienie bieżących danych określonego produktu.

```txt
Path:
    /api/environment/{environmentId}/setonhand/{inventorySystem}/bulk
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
            dimensionDataSource: string, # Optional
            dimensions: {
                [key:string]: string,
            },
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifiedDateTimeUTC: datetime,
        },
        ...
    ]
```

W poniższym przykładzie pokazano zawartość przykładowej treści. Zachowanie tego interfejsu API różni się od zachowania interfejsów API, które opisano w sekcji [Tworzenie zdarzeń zmiany dostępnych zapasów](#create-onhand-change-event) we wcześniejszej części tego artykułu. W tym przykładzie ilość produktu *T-shirt* przybiera wartość 1.

```json
[
    {
        "id": "123456",
        "organizationId": "SCM_IV",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "posSiteId": "iv_postman_site",
            "posLocationId": "iv_postman_location",
            "posMachineId": "0001"
        },
        "quantities": {
            "pos": {
                "inbound": 1
            }
        }
    }
]
```

## <a name="create-reservation-events"></a>Tworzenie zdarzeń rezerwacji

Aby korzystać z interfejsu API *rezerwacji*, należy włączyć funkcję rezerwacji i dokończyć konfigurację rezerwacji. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfiguracja rezerwacji (opcjonalna)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Tworzenie jednego zdarzenia rezerwacji

Rezerwacji można dokonać w różnych ustawieniach źródła danych. Aby skonfigurować ten typ rezerwacji, najpierw określ źródło danych w parametrze `dimensionDataSource`. Następnie w parametrze `dimensions` określ wymiary zgodnie z ustawieniami wymiarów w docelowym źródle danych.

Po wywołaniu interfejsu API rezerwacji można kontrolować walidacje rezerwacji, określając parametr logiczny `ifCheckAvailForReserv` w treści żądania. Wartość `True` oznacza, że walidacja jest wymagana, podczas gdy wartość `False` oznacza, że walidacja nie jest wymagana. Wartością domyślną jest `True`.

Aby wycofać rezerwację lub cofnąć rezerwację określonych ilości magazynowych, ustaw ilość na wartość ujemną i ustaw parametr `ifCheckAvailForReserv` na `False`, aby pominąć weryfikację. Istnieje również dedykowany interfejs API cofania rezerwacji do wykonania tej samej czynności. Różnica polega tylko na sposobu wywoływania tych dwóch interfejsów API. Wycofanie określonego zdarzenia rezerwacji przy użyciu `reservationId` z interfejsem API *wycofaj rezerwację* jest łatwiejsze. Aby uzyskać więcej informacji, zobacz sekcję [_Wycofanie rezerwacji jednego zdarzenia rezerwacji_](#reverse-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve
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
        dimensionDataSource: string,
        dimensions: {
            [key:string]: string,
        },
        quantityDataSource: string, # optional
        quantities: {
            [dataSourceName:string]: {
                [key:string]: number,
            },
        },
        modifier: string,
        quantity: number,
        ifCheckAvailForReserv: boolean,
    }
```

W poniższym przykładzie pokazano zawartość przykładowej treści.

```json
{
    "id": "reserve-0",
    "organizationId": "SCM_IV",
    "productId": "iv_postman_product",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softReservOrdered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "siteId": "iv_postman_site",
        "locationId": "iv_postman_location",
        "colorId": "red",
        "sizeId&quot;: &quot;small"
    }
}
```

W poniższym przykładzie pokazano odpowiedź pomyślną.

```json
{
    "reservationId": "RESERVATION_ID",
    "id": "ohre~id-822-232959-524",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
``` 

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Tworzenie wielu zdarzeń rezerwacji

Ten interfejs API jest wersją masową [interfejsu API jednego zdarzenia](#create-reservation-events).

```txt
Path:
    /api/environment/{environmentId}/onhand/reserve/bulk
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
            quantities: {
                [dataSourceName:string]: {
                    [key:string]: number,
                },
            },
            modifier: string,
            quantity: number,
            ifCheckAvailForReserv: boolean,
        },
        ...
    ]
```

## <a name="reverse-reservation-events"></a>Zdarzenie wycofania rezerwacji

Interfejs API *Wycofaj rezerwację* służy jako operacja dla zdarzeń [*Rezerwacja*](#create-reservation-events). Umożliwia wycofanie zdarzenia rezerwacji określone przez `reservationId` lub zmniejszenie ilości rezerwacji.

### <a name="reverse-one-reservation-event"></a><a name="reverse-one-reservation-event"></a>Wycofanie jednego zdarzenia rezerwacji

Podczas tworzenia rezerwacji, identyfikator `reservationId` zostanie uwzględniony w treści odpowiedzi. Musisz podać taki sam `reservationId`, aby anulować rezerwację, i uwzględnić ten sam `organizationId` i `dimensions` użyte w wywołaniu interfejsu API rezerwacji. Na koniec należy określić wartość `OffsetQty` reprezentującą liczbę towarów, które mają zostać zwolnione z poprzedniej rezerwacji. Rezerwację można w całości lub częściowo wycofać w zależności od podanej wartości `OffsetQty`. Jeśli na przykład zarezerwowano *100* jednostek towaru, można określić `OffsetQty: 10`, aby cofnąć rezerwację *10* z początkowo zarezerwowanej ilości.

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve
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
        reservationId: string,
        dimensions: {
            [key:string]: string,
        },
        OffsetQty: number
    }
```

Poniższy kod pokazuje przykład treści zawartości.

```json
{
    "id": "unreserve-0",
    "organizationId": "SCM_IV",
    "reservationId": "RESERVATION_ID",
    "dimensions": {
        "siteid":"iv_postman_site",
        "locationid":"iv_postman_location",
        "ColorId": "red",
        "SizeId&quot;: &quot;small"
    },
    "OffsetQty": 1
}
```

Poniższy kod pokazuje przykład pomyślnej treści odpowiedzi.

```json
{
    "reservationId": "RESERVATION_ID",
    "totalInvalidOffsetQtyByReservId": 0,
    "id": "ohoe~id-823-11744-883",
    "processingStatus": "success",
    "message": "",
    "statusCode": 200
}
```

> [!NOTE]
> W treści odpowiedzi, jeśli `OffsetQty` jest mniejsze lub równe ilości rezerwacji, stan `processingStatus` będzie „*powodzenie*” i `totalInvalidOffsetQtyByReservId` będzie *0*.
>
> Jeśli `OffsetQty` jest większe niż zarezerwowana kwota, stan `processingStatus` będzie „*partialSuccess*” i `totalInvalidOffsetQtyByReservId` będzie różnicą między `OffsetQty` a zarezerwowaną kwotą.
>
>Na przykład, jeśli rezerwacja ma ilość *10* i `OffsetQty` ma wartość *12*, `totalInvalidOffsetQtyByReservId` będzie *2*.

### <a name="reverse-multiple-reservation-events"></a><a name="reverse-multiple-reservation-events"></a>Wycofanie wielu zdarzeń rezerwacji

Ten interfejs API jest wersją masową [interfejsu API jednego zdarzenia](#reverse-one-reservation-event).

```txt
Path:
    /api/environment/{environmentId}/onhand/unreserve/bulk
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
            reservationId: string,
            dimensions: {
                [key:string]: string,
            },
            OffsetQty: number
        }
        ...
    ]
```

## <a name="query-on-hand"></a>Zapytanie o dostępne zapasy

Użyj interfejsu API *zapytania o dostępne zapasy* do pobierania bieżących danych o dostępnych zapasach produktów. Interfejs API aktualnie obsługuje wykonywanie zapytań o maksymalnie 5000 pojedynczych towarów według wartości `productID`. W każdym zapytaniu można określić również kilka wartości `siteID` i `locationID`. Maksymalny limit jest określony przez następujące równanie:

*NumOf(SiteID) \* NumOf(LocationID) <= 100*.

### <a name="query-by-using-the-post-method"></a><a name="query-with-post-method"></a>Zapytanie przy użyciu metody POST

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

W treści tego żądania `dimensionDataSource` to wciąż opcjonalny parametr. Jeśli nie jest ustawiony, `filters` będą traktowane jako *wymiary bazowe*. Istnieją cztery wymagane pola dla elementu `filters`: `organizationId`, `productId`, `siteId` i `locationId`.

- Element `organizationId` powinien zawierać tylko jedną wartość, ale nadal jest tablicą.
- Element `productId` może zawierać jedną lub więcej wartości. Jeśli jest to pusta tablica, zostaną zwrócone wszystkie produkty.
- `siteId` i `locationId` są używane w dodatku Widoczność zapasów podczas partycjonowania. Można określić więcej niż jedną wartość `siteId` i `locationId` w żądaniu *kwerendy o dane na dane zamówienie*. W bieżącym wydaniu należy określić obie wartości `siteId` i `locationId`.

Sugerujemy, by użyć parametru `groupByValues` powinny dla zgodności z konfiguracją na potrzeby indeksowania. Więcej informacji można znaleźć w temacie [Konfiguracja hierarchii indeksów produktów](./inventory-visibility-configuration.md#index-configuration).

Parametr `returnNegative` określa, czy wyniki zawierają wartości ujemne.

> [!NOTE]
> Jeśli włączono harmonogram dostępnych zmian i dostępne funkcje (ATP), zapytanie może również zawierać parametr logiczny `QueryATP`, który kontroluje, czy wyniki zapytania zawierają informacje ATP. Aby uzyskać więcej informacji i przykładów, zobacz [Widoczność zapasów — harmonogramy i zmiany dostępnych zapasów oraz dostępność zapasów](inventory-visibility-available-to-promise.md).

W poniższym przykładzie pokazano zawartość przykładowej treści.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "siteId": ["iv_postman_site"],
        "locationId": ["iv_postman_location"],
        "colorId": ["red"]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

Poniższe przykłady pokazują sposób wykonywania zapytań dla wszystkich produktów w określonej witrynie i w określonej lokalizacji.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "siteId": ["iv_postman_site"],
        "locationId": ["iv_postman_location"],
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

### <a name="query-by-using-the-get-method"></a><a name="query-with-get-method"></a>Zapytanie przy użyciu metody GET

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

Oto przykładowy adres URL GET. To żądanie GET jest dokładnie takie samo, jak przykładowe księgowanie przedstawione wcześniej.

```txt
/api/environment/{environmentId}/onhand?organizationId=SCM_IV&productId=iv_postman_product&siteId=iv_postman_site&locationId=iv_postman_location&colorId=red&groupBy=colorId,sizeId&returnNegative=true
```

### <a name="exact-query-by-using-the-post-method"></a><a name="exact-query-with-post-method"></a>Dokładne zapytanie przy użyciu metody POST

```txt
Path:
    /api/environment/{environmentId}/onhand/exactquery
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
            dimensions: string[],
            values: string[][],
        },
        groupByValues: string[],
        returnNegative: boolean,
    }
```

W treści tego żądania `dimensionDataSource` to opcjonalny parametr. Jeśli nie jest ustawiony, `dimensions` w `filters` będą traktowane jako *wymiary bazowe*. Istnieją cztery wymagane pola dla elementu `filters`: `organizationId`, `productId`, `dimensions` i `values`.

- Element `organizationId` powinien zawierać tylko jedną wartość, ale nadal jest tablicą.
- Element `productId` może zawierać jedną lub więcej wartości. Jeśli jest to pusta tablica, zostaną zwrócone wszystkie produkty.
- W tablicy `dimensions`są wymagane`siteId` i `locationId`, ale mogą pojawiać się razem z innymi elementami w dowolnej kolejności.
- `values` może zawierać co najmniej jeden odrębnych tu należy do wartości odpowiadających `dimensions`.

`dimensions` w `filters` będą automatycznie dodane do `groupByValues`.

Parametr `returnNegative` określa, czy wyniki zawierają wartości ujemne.

W poniższym przykładzie pokazano zawartość przykładowej treści.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": ["iv_postman_product"],
        "dimensions": ["siteId", "locationId", "colorId"],
        "values" : [
            ["iv_postman_site", "iv_postman_location", "red"],
            ["iv_postman_site", "iv_postman_location", "blue"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

Poniższe przykłady pokazują sposób wykonywania zapytań dla wszystkich produktów w wielu witrynach i lokalizacjach.

```json
{
    "filters": {
        "organizationId": ["SCM_IV"],
        "productId": [],
        "dimensions": ["siteId", "locationId"],
        "values" : [
            ["iv_postman_site_1", "iv_postman_location_1"],
            ["iv_postman_site_2", "iv_postman_location_2"],
        ]
    },
    "groupByValues": ["colorId", "sizeId"],
    "returnNegative": true
}
```

## <a name="available-to-promise"></a>Dostępność zapasów

Widoczność zapasów można skonfigurować, aby było można zaplanować przyszłe zmiany dostępnych zapasów i obliczyć ilości ATP. ATP to ilość towaru, która jest dostępna i którą można obiecać klientowi w następnym okresie. Użycie kalkulacji ATP może znacznie zwiększyć twoje możliwości realizacji zamówień. Aby uzyskać informacje o tym, jak włączyć tę funkcję i jak wchodzić w interakcję z widocznością zapasów za pośrednictwem interfejsu API po włączeniu tej funkcji, zobacz [Harmonogramy zmian widoczności zapasów na bieżąco i dostępne do obiecania](inventory-visibility-available-to-promise.md#api-urls).

## <a name="allocation"></a>Alokacja

Interfejsy API związane z alokacją znajdują się w [Przydział widoczności zapasów](inventory-visibility-allocation.md#using-allocation-api).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
