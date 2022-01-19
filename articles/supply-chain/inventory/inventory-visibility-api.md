---
title: Publiczne interfejsy API dodatku Widoczność magazynu
description: W tym temacie opisano publiczne interfejsy API udostępniane przez dodatek Widoczność magazynu.
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
ms.openlocfilehash: 92c427d3063c34f263d5bc449be6fac695b5912d
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952634"
---
# <a name="inventory-visibility-public-apis"></a>Publiczne interfejsy API dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

W tym temacie opisano publiczne interfejsy API udostępniane przez dodatek Widoczność magazynu.

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
| /api/environment/{environmentId}/onhand/indexquery | Księguj | [Zapytanie przy użyciu metody POST](#query-with-post-method) |
| /api/environment/{environmentId}/onhand | Pobierz | [Zapytanie przy użyciu metody GET](#query-with-get-method) |

Firma Microsoft dostarcza kolekcję gotowych do użycia żądań *Postman*. Kolekcję można zaimportować do oprogramowania *Postman*, korzystając z następującego udostępnionego łącza: <https://www.getpostman.com/collections/90bd57f36a789e1f8d4c>

> [!NOTE]
> Część {environmentId} ścieżki jest identyfikatorem środowiska w usługach Microsoft Dynamics Lifecycle Services (LCS).
> 
> API zbiorcze może zwrócić maksymalnie 512 rekordów dla każdego żądania.

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

Token zabezpieczeń platformy służy do wywołania publicznego interfejsu API Widoczność magazynu. Dlatego należy wygenerować _token Azure Active Directory (Azure AD)_ przy użyciu aplikacji Azure AD. Następnie należy użyć tokenu Azure AD, aby uzyskać _token dostępu_ z usługi zabezpieczeń.

Firma Microsoft dostarcza kolekcję gotowych do pobierania tokenów *Postman*. Kolekcję można zaimportować do oprogramowania *Postman*, korzystając z następującego udostępnionego łącza: <https://www.getpostman.com/collections/496645018f96b3f0455e>

Procedura uzyskiwania tokenu usługi zabezpieczeń jest następująca.

1. Zaloguj się do portalu Azure i użyj go, aby znaleźć wartości `clientId` i `clientSecret` dla swojej aplikacji Dynamics 365 Supply Chain Management.
1. Pobierz token usługi Azure AD (`aadToken`), przesyłając żądanie HTTP z następującymi właściwościami:

   - **URL:** `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
   - **Metoda:** `GET`
   - **Treść (dane formularza):**

     | Klucz           | Wartość                                |
     | ------------- | ------------------------------------ |
     | client_id     | ${aadAppId}                          |
     | client_secret | ${aadAppSecret}                      |
     | grant_type    | client_credentials                   |
     | resource      | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |

   Odpowiedź powinna zawierać token Azure AD (`aadToken`). Powinna ona przypominać następujący przykład.

   ```json
   {
       "token_type": "Bearer",
       "expires_in": "3599",
       "ext_expires_in": "3599",
       "expires_on": "1610466645",
       "not_before": "1610462745",
       "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
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
       "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
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
> Gdy do wywołania interfejsów API publicznych widoczności zapasów jest używać kolekcji żądań *Postman*, należy dla każdego żądania dodać token okaziciela. Aby znaleźć token okaziciela, wybierz kartę **Autoryzacja** pod adresem URL żądania, wybierz typ **tokenu okaziciela** i skopiuj token dostępu, który został pobrany w ostatnim kroku. W dalszych częściach tego tematu, `$access_token` będzie używany do reprezentowania tokena, który został pobrany w ostatnim kroku.

## <a name="create-on-hand-change-events"></a><a name="create-onhand-change-event"></a>Tworzenie zdarzeń zmiany dostępnych zapasów

Istnieją dwa interfejsy API do tworzenia zdarzeń zmiany dostępnych zapasów:

- Tworzenie jednego rekordu: `/api/environment/{environmentId}/onhand`
- Tworzenie wielu rekordów: `/api/environment/{environmentId}/onhand/bulk`

W poniższej tabeli podsumowano znaczenie poszczególnych pól w treści JSON.

| Identyfikator pola | opis |
|---|---|
| `id` | Unikatowy identyfikator określonego zdarzenia zmiany. Ten identyfikator służy do zapewnienia, że jeśli komunikacja z usługą nie powiedzie się w trakcie księgowania, to samo zdarzenie wysłane ponownie nie zostanie zliczone dwukrotnie w systemie. |
| `organizationId` | Identyfikator organizacji połączonej ze zdarzeniem. Wartość jest mapowana na identyfikator organizacji lub obszaru danych w Supply Chain Management. |
| `productId` | Identyfikator produktu. |
| `quantities` | Ilość, o którą musi zostać zmieniona dostępna ilość. Jeśli na przykład na półce zostanie dołożonych 10 nowych książek, ta wartość będzie wynosić `quantities:{ shelf:{ received: 10 }}`. Jeśli trzy książki zostaną usunięte z półki lub sprzedane, ta wartość będzie wynosić `quantities:{ shelf:{ sold: 3 }}`. |
| `dimensionDataSource` | Źródło danych wymiarów używanych w zdarzeniu zmiany księgowania i zapytaniu. W przypadku określenia źródła danych można wykorzystać niestandardowe wymiary z określonego źródła danych. Dodatek Widoczność magazynu może używać konfiguracji wymiarów do mapowania niestandardowych wymiarów na ogólne wymiary domyślne. Jeśli nie określiło wartości `dimensionDataSource`, w zapytaniach można stosować tylko ogólne [wymiary podstawowe](inventory-visibility-configuration.md#data-source-configuration-dimension). |
| `dimensions` | Dynamiczna para klucz-wartość. Te wartości są mapowane na niektóre wymiary w Supply Chain Management. Można jednak dodać również wymiary niestandardowe (na przykład _Źródło_), aby wskazać, czy zdarzenie pochodzi z Supply Chain Management, czy z systemu zewnętrznego. |

> [!NOTE]
> Parametry `SiteId` i `LocationId` konstruują [konfigurację partycji](inventory-visibility-configuration.md#partition-configuration). Należy je zatem określić w wymiarach podczas tworzenia zdarzeń zmiany dostępnego czasu, określania lub zastępowania ilości w dostępnej ilości albo tworzenia zdarzeń rezerwacji.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensionDataSource": "pos",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "PosMachineId": "0001",
        "ColorId": "Red"
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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
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
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
            "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId&quot;: &quot;0001"
        },
        "quantities": {
            "pos": { "inbound": 1 }
        }
    },
    {
        "id": "654321",
        "organizationId": "usmf",
        "productId": "Pants",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId&quot;: &quot;black"
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

W poniższym przykładzie pokazano zawartość przykładowej treści. Zachowanie tego interfejsu API różni się od zachowania interfejsów API, które opisano w sekcji [Tworzenie zdarzeń zmiany dostępnych zapasów](#create-onhand-change-event) we wcześniejszej części tego tematu. W tym przykładzie ilość produktu *T-shirt* przybiera wartość 1.

```json
[
    {
        "id": "123456",
        "organizationId": "usmf",
        "productId": "T-shirt",
        "dimensionDataSource": "pos",
        "dimensions": {
             "PosSiteId": "1",
            "PosLocationId": "11",
            "PosMachineId": "0001"
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

Aby korzystać z interfejsu API *rezerwacji*, należy otworzyć funkcję rezerwacji i dokończyć konfigurację rezerwacji. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Konfiguracja rezerwacji (opcjonalna)](inventory-visibility-configuration.md#reservation-configuration).

### <a name="create-one-reservation-event"></a><a name="create-one-reservation-event"></a>Tworzenie jednego zdarzenia rezerwacji

Rezerwacji można dokonać w różnych ustawieniach źródła danych. Aby skonfigurować ten typ rezerwacji, najpierw określ źródło danych w parametrze `dimensionDataSource`. Następnie w parametrze `dimensions` określ wymiary zgodnie z ustawieniami wymiarów w docelowym źródle danych.

Po wywołaniu interfejsu API rezerwacji można kontrolować walidacje rezerwacji, określając parametr logiczny `ifCheckAvailForReserv` w treści żądania. Wartość `True` oznacza, że walidacja jest wymagana, podczas gdy wartość `False` oznacza, że walidacja nie jest wymagana. Wartością domyślną jest `True`.

Aby anulować rezerwację lub cofnąć rezerwację określonych ilości magazynowych, ustaw ilość na wartość ujemną i ustaw parametr `ifCheckAvailForReserv` na `False`, aby pominąć weryfikację.

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
    "organizationId": "usmf",
    "productId": "T-shirt",
    "quantity": 1,
    "quantityDataSource": "iv",
    "modifier": "softreservordered",
    "ifCheckAvailForReserv": true,
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId&quot;: &quot;Small"
    }
}
```

### <a name="create-multiple-reservation-events"></a><a name="create-multiple-reservation-events"></a>Tworzenie wielu zdarzeń rezerwacji

Ten interfejs API jest wersją masową [interfejsu API jednego zdarzenia](#create-one-reservation-event).

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

## <a name="query-on-hand"></a>Zapytanie o dostępne zapasy

Użyj interfejsu API _zapytania o dostępne zapasy_ do pobierania bieżących danych o dostępnych zapasach produktów. Interfejs API aktualnie obsługuje wykonywanie zapytań o maksymalnie 100 pojedynczych towarów według wartości `ProductID`. W każdym zapytaniu można określić również kilka wartości `SiteID` i `LocationID`. Maksymalny limit jest zdefiniowany jako `NumOf(SiteID) * NumOf(LocationID) <= 100`.

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

Parametr `groupByValues` powinny być zgodne z konfiguracją na potrzeby indeksowania. Więcej informacji można znaleźć w temacie [Konfiguracja hierarchii indeksów produktów](./inventory-visibility-configuration.md#index-configuration).

Parametr `returnNegative` określa, czy wyniki zawierają wartości ujemne.

W poniższym przykładzie pokazano zawartość przykładowej treści.

```json
{
    "dimensionDataSource": "pos",
    "filters": {
        "organizationId": ["usmf"],
        "productId": ["T-shirt"],
        "siteId": ["1"],
        "LocationId": ["11"],
        "ColorId": ["Red"]
    },
    "groupByValues": ["ColorId", "SizeId"],
    "returnNegative": true
}
```

Poniższe przykłady pokazują sposób wykonywania zapytań dla wszystkich produktów w określonej witrynie i w określonej lokalizacji.

```json
{
    "filters": {
        "organizationId": ["usmf"],
        "productId": [],
        "siteId": ["1"],
        "LocationId": ["11"],
    },
    "groupByValues": ["ColorId", "SizeId"],
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
/api/environment/{environmentId}/onhand?organizationId=usmf&productId=T-shirt&SiteId=1&LocationId=11&ColorId=Red&groupBy=ColorId,SizeId&returnNegative=true
```

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
