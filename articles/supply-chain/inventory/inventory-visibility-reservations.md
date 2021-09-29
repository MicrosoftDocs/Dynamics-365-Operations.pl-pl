---
title: Rezerwacje dodatku Widoczność magazynu
description: W tym temacie opisano sposób skonfigurowania funkcji rezerwacji w celu tworzenia rezerwacji, zużywania rezerwacji i/lub rezerwowania określonych ilości zapasów za pomocą dodatku Widoczność magazynu.
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
ms.openlocfilehash: 4a85520c0911bb7eed5842b3fd5bd706009351e5
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500362"
---
# <a name="inventory-visibility-reservations"></a>Rezerwacje dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

W tym temacie opisano sposób skonfigurowania funkcji rezerwacji w celu tworzenia rezerwacji, zużywania rezerwacji i/lub rezerwowania określonych ilości zapasów za pomocą dodatku Widoczność magazynu.

Rezerwacje oznaczą ilość zapasów, która będzie używana w przyszłości. Podczas tworzenia rezerwacji system uniemożliwia innym zamówieniom rezerwowanie lub zużywanie zarezerwowanych towarów do czasu, aż rezerwacja zostanie zużyta lub anulowana. Rezerwacje są tworzone, zużywane i anulowane za pomocą wywołań interfejsu API w usłudze Widoczność magazynu.

Opcjonalnie można skonfigurować rozwiązanie Microsoft Dynamics 365 Supply Chain Management (i inne systemy innych firm), aby ilość zarezerwowana przy użyciu dodatku Widoczność magazynu była automatycznie kompensowana. Ilość kompensowana jest usuwana z rekordów rezerwacji w dodatku Widoczność magazynu.

Po włączeniu funkcji rezerwacji rozwiązanie Supply Chain Management automatycznie staje się gotowe do kompensacji rezerwacji, które są dokonywane za pomocą dodatku Widoczność magazynu.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Włączanie i konfigurowanie funkcji rezerwacji

Aby włączyć funkcję rezerwacji, należy wykonać następujące kroki.

1. Zaloguj się do Power Apps i otwórz dodatek **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Zarządzanie funkcjami** włącz funkcję *OnHandReservation*.
1. Zaloguj się do modułu Supply Chain Management.
1. Przejdź do obszaru roboczego **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** i włącz funkcję *Integracja z dodatkiem Widoczność magazynu z przesunięciem rezerwacji* (wymagana jest wersja 10.0.22 lub nowsza).
1. Przejdź do **Zarządzanie zapasami \> Ustawienia \> Parametry integracji dodatku Widoczność magazynu**, otwórz kartę **Przesunięcie rezerwacji** i ustaw następujące ustawienia:
    - **Włącz przesunięcie rezerwacji** — aby włączyć tę funkcję, ustaw wartość *Tak*.
    - **Modyfikator przesunięcia rezerwacji** — wybierz stan transakcji magazynowej, który będzie powodować przesunięcie rezerwacji w dodatku Widoczność magazynu. To ustawienie określa etap przetwarzania zamówienia, który wyzwala przesunięcia. Etap jest śledzony według stanu transakcji magazynowej zamówienia. Wybierz jedną z następujących opcji:
        - *Na zamówienie* — w przypadku stanu *W transakcji* po utworzeniu zamówienia będzie wysyłane żądanie przeciwstawne. Ilość przesunięcia będzie ilością z utworzonego zamówienia.
        - *Rezerwa* — w przypadku stanu *Zarezerwuj zamówioną transakcję* zamówienie wysyła żądanie przeciwstawne, gdy zostanie zarezerwowane, skompletowane, zaksięgowane z listą wysyłkową lub zafakturowane. Żądanie zostanie wyzwolone tylko raz, podczas pierwszego kroku w momencie wystąpienia wymienionego procesu. Ilość przesunięcia to ilość, w której stan transakcji magazynowej zmienił się z *Zamówione* na *Zamówione zarezerwowane* (lub późniejszy) w odpowiednim wierszu zamówienia.

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Używanie funkcji rezerwacji w dodatku Widoczność magazynu

Po wywołaniu interfejsu API rezerwacji system oznacza rezerwację określonych towarów i ilości. Zdefiniuj hierarchię rezerwacji i zaksięguj żądania zgodne z hierarchią rezerwacji. Rezerwacji można następnie dokonać, wywołując bezpośrednio interfejsy API rezerwacji.

### <a name="configure-the-reservation-hierarchy"></a>Konfigurowanie hierarchii rezerwacji

Hierarchia rezerwacji opisuje sekwencję wymiarów, które muszą być określone podczas dokonywania rezerwacji. Działa to w taki sam sposób, jak hierarchia indeksów w przypadku zapytań o dostępne.

Hierarchia rezerwacji może się różnić od hierarchii indeksów. Ta niezależność umożliwia wdrożenie zarządzania kategoriami, w którym użytkownicy mogą rozbić wymiary na szczegóły, aby określić wymagania dotyczące dokonywania precyzyjniejszych rezerwacji.

Aby skonfigurować hierarchię rezerwacji wstępnej w Power Apps, otwórz stronę **Konfiguracja**, a następnie na karcie **Hierarchia rezerwacji wstępnej** skonfiguruj hierarchię rezerwacji, dodając i/lub modyfikując wymiary i ich poziomy hierarchii.

Hierarchia rezerwacji wstępnej powinna zawierać składniki `SiteId` i `LocationId`, ponieważ konstruują one konfigurację partycji.

Aby uzyskać więcej informacji o sposobie konfigurowania rezerwacji, zobacz temat [Konfiguracja rezerwacji](inventory-visibility-configuration.md#reservation-configuration).

### <a name="call-the-reservation-api"></a>Wywoływanie interfejsu API rezerwacji

Rezerwacje są dokonywane w usłudze Widoczność magazynu przez przesłanie żądania POST do adresu URL usługi, takiego jak `/api/environment/{environment-ID}/onhand/reserve`.

W przypadku rezerwacji treść żądania musi zawierać identyfikator organizacji, identyfikator produktu, zarezerwowane ilości i wymiary. Żądanie generuje unikatowy identyfikator rezerwacji dla każdego rekordu rezerwacji. Rekord rezerwacji zawiera unikatową kombinację identyfikatora produktu i wymiarów.

Po wywołaniu interfejsu API rezerwacji można kontrolować walidacje rezerwacji, określając parametr logiczny `ifCheckAvailForReserv` w treści żądania. Wartość `True` oznacza, że walidacja jest wymagana, podczas gdy wartość `False` oznacza, że walidacja nie jest wymagana. Wartością domyślną jest `True`.

Aby anulować rezerwację lub cofnąć rezerwację określonych ilości magazynowych, ustaw ilość na wartość ujemną i ustaw parametr `ifCheckAvailForReserv` na `False`, aby pominąć weryfikację.

Oto przykładowa treść żądania.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "SoftReservOrdered",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

## <a name="offset-reservations-in-supply-chain-management"></a>Kompensowanie rezerwacji w rozwiązaniu Supply Chain Management

W przypadku stanów transakcji magazynowych, które zawierają określony modyfikator kompensacji rezerw, aktualizacja transakcji będzie przeciwstawna do odpowiedniego rekordu rezerwacji, jeśli są spełnione następujące warunki:

- Identyfikator rezerwacji w transakcji magazynowej pasuje do identyfikatora rezerwacji rekordu rezerwacji w usłudze Widoczność magazynu.
- Wymiary transakcji magazynowej są identyczne jak wymiary rekordu rezerwacji w usłudze Widoczność magazynu.
- Zmiany stanu transakcji magazynowej wyzwalają kompensacje dla rezerwacji, gdy stan transakcji magazynowej odzwierciedla fakt, że proces zamówienia został ukończony lub pominięty.

Ilość przeciwstawna jest zgodna z ilością zapasów określoną w transakcjach magazynowych. Kompensacja nie skutkuje, jeśli w usłudze Widoczność magazynu nie pozostanie żadna zarezerwowana ilość.

### <a name="set-up-the-reservation-offset-modifier"></a>Konfigurowanie modyfikatora przesunięcia rezerwacji

Jeśli nie zostało to zrobione wcześniej, należy skonfigurować modyfikator rezerwacji zgodnie z opisem w temacie [Włączanie i konfigurowanie funkcji rezerwacji](#turn-on).

### <a name="set-up-reservation-ids"></a>Konfigurowanie identyfikatorów rezerwacji

Identyfikator rezerwacji jednoznacznie oznacza rekord rezerwacji w dodatku Widoczność magazynu. W Supply Chain Management użytkownicy umieszczają rezerwacje w wierszach zamówienia, aby oznaczyć przeciwstawne dla odpowiedniego rekordu rezerwacji.

Aby skonfigurować identyfikatory rezerwacji w Supply Chain Management, należy wykonać następujące kroki.

1. Otwórz zamówienie sprzedaży (na przykład ze strony **Wszystkie zamówienia sprzedaży**).
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** na pasku narzędzi wybierz kolejno opcje **Aktualizacja wiersza \> Zapasy \> Integracja dodatku Widoczność magazynu**.
1. Wprowadź odpowiednie identyfikatory rezerwacji.

Zmiana stanu zapasów odpowiada konfiguracji modyfikatora kompensacji.
