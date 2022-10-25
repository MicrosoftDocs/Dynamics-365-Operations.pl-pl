---
title: Parametry proaktywnego czatu modułu czatu rozwiązania Commerce
description: W tym artykule opisano parametry proaktywnego czatu modułu Commerce w aplikacji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691076"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Parametry proaktywnego czatu modułu czatu rozwiązania Commerce

[!include [banner](includes/banner.md)]

W tym artykule opisano parametry proaktywnego czatu modułu Commerce z usługami Obsługa wielokanałowa dla Customer Service i Czat w rozwiązaniu Commerce przy użyciu usługi Power Virtual Agents w aplikacji Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Właściwości proaktywnego czatu

Właściwości proaktywnego czatu znajdują się w okienku właściwości modułów czatu rozwiązania Commerce z usługą Obsługa wielokanałowa dla Customer Service oraz czatu rozwiązania Commerce z usługą Power Virtual Agents w kreatorze witryn rozwiązania Commerce.

> [!NOTE]
> Domyślnie wszystkie wymienione tutaj właściwości proaktywnego czatu są puste. Zaleca się, aby dowiedzieć się więcej o tych właściwościach i ustawiać je tylko w razie potrzeby. To podejście pozwoli ograniczyć liczbę wyzwoleń proaktywnych czatów.

### <a name="proactive-chat"></a>Proaktywny czat

| Nazwa wyświetlana | Opis | Wartość domyślna |
|---------------|-------------|---------------|
| Włączone | Aktywnie angażowanie klientów na podstawie różnych wyzwalaczy. | Wyłączono |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. | Pusty |

### <a name="wait-time-proactive-chat"></a>Czas oczekiwania (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Czas oczekiwania (s) | Czas (w sekundach), który użytkownicy witryny spędzają na stronie witryny, zanim zostanie wyzwolony proaktywny czat. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="number-of-page-visits-proactive-chat"></a>Liczba odwiedzin strony (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Liczba odwiedzin strony | Liczba odwiedzin strony przed uruchomieniem proaktywnego czatu. Użytkownicy witryny muszą najpierw zaakceptować monit na banerze zgody na pliki cookie. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="specific-pages-proactive-chat"></a>Określone strony (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Strony | Lista stron, których odwiedzenie wyzwoli proaktywny czat. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="from-specific-pages-proactive-chat"></a>Od określonych stron (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Strony | Lista stron, których opuszczenie przez użytkowników wyzwoli proaktywny czat. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="specific-countryregion-proactive-chat"></a>Określony kraj/region (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Kod kraju | Użytkownicy odwiedzający z określonych krajów lub regionów wyzwolą proaktywny czat. Kody kraju/regionu powinny mieć zawierać dwie wielkie litery (na przykład **US**). |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="date-range-proactive-chat"></a>Zakres dat (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Data rozpoczęcia (dd/mm/rrrr) | Data, dla której lub po której zostanie wyzwolony proaktywny czat. |
| Data zakończenia (dd/mm/rrrr) | Data, dla której lub przed którą zostanie wyzwolony proaktywny czat. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="total-amount-in-cart-proactive-chat"></a>Łączna kwota w koszyku (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Minimalna | Minimalna kwota pieniężna (włącznie) w koszyku, która wywoła proaktywny czat, gdy użytkownicy odwiedzą stronę koszyka. |
| Maksymalna | Maksymalna kwota pieniężna (włącznie) w koszyku, która wywoła proaktywny czat, gdy użytkownicy odwiedzą stronę koszyka. |
|Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>Łączna liczba pozycji w koszyku (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Minimalna | Minimalna liczba pozycji (włącznie) w koszyku, która wywoła proaktywny czat, gdy użytkownicy odwiedzą stronę koszyka. |
| Maksymalna | Maksymalna liczba pozycji (włącznie) w koszyku, która wywoła proaktywny czat, gdy użytkownicy odwiedzą stronę koszyka. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

### <a name="specific-products-in-cart-proactive-chat"></a>Określone produkty w koszyku (proaktywny czat)

| Nazwa wyświetlana | Opis |
|---------------|-------------|
| Identyfikator/jednostka SKU produktów | Lista identyfikatorów/numerów jednostek magazynowych (SKU), które wyzwolą proaktywny czat podczas wizyty użytkowników na stronie koszyka. |
| Powitanie na czacie | Wiadomość powitalna używana po wyzwoleniu proaktywnego czatu. |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie funkcji czatu rozwiązania Commerce](commerce-chat-overview.md)

[Moduł Czat rozwiązania Commerce z Obsługą wielokanałową dla Customer Service](commerce-chat-module.md)

[Czat rozwiązania Commerce z modułem Power Virtual Agents](chat-module-pva.md)
