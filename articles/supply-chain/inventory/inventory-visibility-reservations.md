---
title: Rezerwacje dodatku Inventory Visibility
description: W tym artykule opisano sposób skonfigurowania funkcji rezerwacji w celu tworzenia rezerwacji, zużywania rezerwacji i/lub rezerwowania określonych ilości zapasów za pomocą dodatku Widoczność magazynu.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0ae0589f8bac7ebf9b43cf0f3bc02680d324b29b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762749"
---
# <a name="inventory-visibility-reservations"></a>Rezerwacje dodatku Inventory Visibility

[!include [banner](../includes/banner.md)]

W tym artykule opisano typowe przypadku rezerwacji miękkich i opisano sposób ich skonfigurowania w widoczności zapasów. Znajdują się w nim informacje dotyczące tworzenia rezerwacji miękkich, kompensacji z fizycznego zużycia oraz korygowania lub niezarezerwowania określonych ilości zapasów.

## <a name="sample-use-case-for-soft-reservation"></a>Przykładowy przypadek użycia do rezerwacji miękkiej

Rezerwacje miękkie pomagają organizacjom w osiągnięciu pojedynczego źródła informacji o dostępnym zapasie, zwłaszcza w trakcie procesu realizacji zamówienia. Ta funkcja jest przydatna w organizacjach, w których istnieją następujące warunki:

- Organizacja ma co najmniej dwa różne systemy, które są bezpośrednio związane z zamówieniami wychodzącymi.
- Organizacja jest bardzo restrykcyjna i chce zapobiec podwójnego rezerwowania zapasów produktów, co może się zdarzyć, jeśli wiele systemów będzie w stanie dokonać rezerwacji ostatniej sztuki towaru. Taka sytuacja jest ograniczona, gdy wszystkie systemy zamówień mogą używać interfejsu API rezerwacji natychmiastowej rezerwacji natychmiastowej w celu widoczności zapasów, co stanowi pojedyncze źródło informacji o dostępności zapasów.

[<img src="media/inventory-visibility-soft-reservation.png" alt="Inventory Visibility soft reservation." title="Miękka rezerwacja widoczności zapasów" width="720" />](media/inventory-visibility-soft-reservation.png)

Na poprzedniej ilustracji pokazano, jak działa rezerwacja programowa, i przedstawiono następujące operacje:

- Początkowy poziom zapasów jest synchronizowany z widocznością zapasów z poziomu rozwiązania Microsoft Dynamics 365 Supply Chain Management.
- Rezerwacje miękkie są księgowane w każdym z kanałów zamówień lub systemów w celu widoczności zapasów. Widoczność zapasów sprawdza dostępność zapasów i próbuje dokonać rezerwacji soft. Jeśli rezerwacja programowa powiedzie się, funkcja Widoczność zapasów dodaje do ilości zarezerwowanej programowo, odejmuje od ilości dostępnej do rezerwacji (AFR) i odpowiada identyfikatorem rezerwacji programowej.
- W tej chwili ilość w magazynie fizycznym pozostaje taka sama.
- Następnie można zsynchronizować pojedyncze lub zagregowane zamówienia z rezerwacją miękką (wiersze zamówienia) z rozwiązaniem Supply Chain Management, aby dokonać twardych rezerwacji i zwolnić do magazynu lub zaktualizować ostateczną ilość zapasów.
- Można skonfigurować system do kompensacji [rezerwacji miękkich podczas](#offset-scm) aktualizacji magazynu fizycznego w Supply Chain Management.

Rezerwacje programowe są zwykle tworzone, wykorzystywane i anulowane przy użyciu wywołań interfejsu API usługi Widoczność zapasów.

> [!NOTE]
> Opcjonalnie można skonfigurować rozwiązanie Supply Chain Management (i inne systemy innych firm), aby ilość zarezerwowana przy użyciu dodatku Widoczność magazynu była automatycznie kompensowana. Ilość kompensowana jest usuwana z rekordów rezerwacji w dodatku Widoczność magazynu.
>
> Domyślnie funkcja przeciwstawna jest włączana automatycznie po włączeniu funkcji rezerwacji soft.

## <a name="turn-on-and-set-up-the-reservation-feature"></a><a name="turn-on"></a>Włączanie i konfigurowanie funkcji rezerwacji

Aby włączyć funkcję rezerwacji, należy wykonać następujące kroki.

1. Zaloguj się do Power Apps i otwórz dodatek **Widoczność magazynu**.
1. Otwórz stronę **Konfiguracja**.
1. Na karcie **Zarządzanie funkcjami** włącz funkcję *OnHandReservation*.
1. Zaloguj się do swojego środowiska Supply Chain Management.
1. Przejdź do obszaru roboczego **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** i włącz funkcję *Integracja z dodatkiem Widoczność magazynu z przesunięciem rezerwacji* (wymagana jest wersja 10.0.22 lub nowsza).
1. Przejdź do **Zarządzanie zapasami \> Ustawienia \> Parametry integracji dodatku Widoczność magazynu**, otwórz kartę **Przesunięcie rezerwacji** i ustaw następujące ustawienia:

    - **Włącz przesunięcie rezerwacji** — aby włączyć tę funkcję, ustaw wartość *Tak*.
    - **Modyfikator przesunięcia rezerwacji** — wybierz stan transakcji magazynowej, który będzie powodować przesunięcie rezerwacji w dodatku Widoczność magazynu. To ustawienie określa etap przetwarzania zamówienia, który wyzwala przesunięcia. Etap jest śledzony według stanu transakcji magazynowej zamówienia. Należy wybrać jedną z następujących opcji:

        - *Na zamówienie* — Zamówienia, które mają status *Na zamówienie*, po utworzeniu wyślą żądanie przesunięcia. Ilość przesunięcia będzie ilością z utworzonego zamówienia (wiersz).
        - *Rezerwacja* — zamówienia o stanie *Rezerwacja* będą wysyłać żądanie przeciwstawne, gdy są zarezerwowane lub fizycznie zarezerwowane. Jeśli stan *rezerwacji* jest księgowany przeciwstawnie, zamówienie wysyła żądanie przeciwstawne z nowym stanem zapasu, który jest najbliższą zarezerwowaniu pobrania (na przykład pobrania, zaksięgowanego dokumentu dostawy lub zafakturowania). Taka sytuacja występuje nawet po pomijaniu rezerwacji w Supply Chain Management i przechodzeniu do innego stanu zapasów (na przykład pominięcia z zwalniania do magazynu w celu pobrania i zapakowania). Żądanie zostanie wyzwolone tylko raz. Jeśli dokument został wywołany podczas pobrania, nie będzie zduplikowany przeciwstawny podczas zaksięgowania dokumentu dostawy. Ilość przesunięcia będzie taka sama, jak ilość w statusie transakcji magazynowej w momencie uruchomienia przesunięcia (innymi słowy *Zarezerwowane zamówione*/*Zarezerwowane Fizyczne* lub nowszy status w odpowiednim wierszu zamówienia).

1. Zaloguj się ponownie w aplikacji Widoczność zapasów, przejdź na stronę **Konfiguracja**, a następnie na karcie **Rezerwacja miękka** przejrzyj domyślną hierarchię rezerwacji miękkich. W razie potrzeby dodaj nowe wymiary do hierarchii.
1. W sekcji **Ustaw mapowanie rezerwacji miękkiej** wyświetl ustawienia domyślne. Domyślnie rezerwowane ilości zapasów będą rejestrowane w odniesieniu do fizycznej miary `softreservephysical` źródła danych `iv`. Obliczona miara *Dostępne do rezerwacji* jest odwzorowywana na `availabletoreserve`. Aby zaktualizować obliczoną miarę `availabletoreserve`, przejdź na stronę **Konfiguracja**, a następnie na karcie **Miara obliczania** rozwiń i zmodyfikuj obliczoną miarę.

Więcej informacji zawiera temat [Konfigurowanie dodatku Widoczność magazynu](inventory-visibility-configuration.md).

> [!NOTE]
> Hierarchia rezerwacji opisuje sekwencję wymiarów, które muszą być określone podczas dokonywania rezerwacji. Działa w ten sam sposób, w jaki hierarchia indeksów działa w przypadku dostępnych zapytań, ale jest używana niezależnie, dzięki czemu użytkownicy mogą określać szczegóły wymiarów w celu dokonywania bardziej precyzyjnych rezerwacji.
>
> Hierarchia rezerwacji wstępnej powinna zawierać składniki `SiteId` i `LocationId`, ponieważ konstruują one konfigurację partycji widoczności zapasów.

Aby uzyskać więcej informacji o sposobie konfigurowania rezerwacji, zobacz temat [Konfiguracja rezerwacji](inventory-visibility-configuration.md#reservation-configuration).

## <a name="use-the-reservation-feature-in-inventory-visibility"></a>Używanie funkcji rezerwacji w dodatku Widoczność magazynu

Po wywołaniu interfejsu API rezerwacji system oznacza rezerwację określonych towarów i ilości.

Oto przykładowy scenariusz i treść przykładowego zapytania interfejsu API. Firma Contoso sprzedaje produkt D0002 (Cabinet) ze swojej witryny handlu elektronicznego. Odbiorca umieszcza zamówienie sprzedaży dla małego czerwonego odbiorcy w witrynie sieci web. Firma Contoso decyduje się zrealizować to zamówienie przy użyciu następujących wymiarów:

- Identyfikator organizacji = usmf
- Witryna = 1
- Magazyn = 11
- Produkt = D0002
- Kolor = czerwony
- Rozmiar = mały

Firma Contoso skonfigurowała już połączenie API z widocznością zapasów z własnego systemu handlu elektronicznego. Po otrzymaniu zamówienia system natychmiast uruchamia wywołanie API w celu dokonania miękkiej rezerwacji szafy w widoczności magazynu.

### <a name="create-soft-reservations-using-the-reservation-api"></a>Tworzenie rezerwacji miękkich przy użyciu interfejsu API rezerwacji

Rezerwacje są dokonywane w usłudze Widoczność magazynu przez przesłanie żądania POST do adresu URL usługi, takiego jak `/api/environment/{environmentId}/onhand/reserve`.

W przypadku rezerwacji treść żądania musi zawierać identyfikator organizacji, identyfikator produktu, zarezerwowane ilości i wymiary.

Po wywołaniu interfejsu API rezerwacji można kontrolować walidacje rezerwacji, określając parametr logiczny `ifCheckAvailForReserv` w treści żądania. Wartość `True` oznacza, że walidacja jest wymagana, podczas gdy wartość `False` oznacza, że walidacja nie jest wymagana. Wartością domyślną jest `True`.

Aby anulować rezerwację lub cofnąć rezerwację określonych ilości magazynowych, ustaw ilość na wartość ujemną i ustaw parametr `ifCheckAvailForReserv` na `False`, aby pominąć weryfikację.

Oto przykład treści żądania, który odwołuje się do zamówienia sprzedaży w poprzednim kontekście.

```json
# Url

#Replace {endpoint} with your system endpoint.
    {endpoint}/api/environment/{environmentId}/onhand/reserve

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "Testrequest-0005",
    "organizationId": "usmf",
    "productId": "D0002",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "red",
        "SizeId": "small"
    },
    "quantityDataSource": "iv",
    "modifier": "softreservphysical",
    "quantity": 1,
    "ifCheckAvailForReserv": true
}
```

Pomyślne żądanie rezerwacji programowej zwraca identyfikator *rezerwacji miękkiej* dla każdego rekordu rezerwacji. Identyfikator rezerwacji miękkiej nie jest unikatowym identyfikatorem pojedynczego rekordu rezerwacji miękkiej, ale kombinacją identyfikatora produktu i wartości wymiarów, które są skojarzone z żądaniem rezerwacji miękkiej. Identyfikator rezerwacji miękkiej można zapisać w wierszu zamówienia podczas synchronizowania pomyślnie zarezerwowanych zamówień z programem Supply Chain Management lub innym systemem ERP w celu przesunięcia.

### <a name="offset-soft-reservations-in-supply-chain-management"></a><a name="offset-scm"></a>Kompensowanie rezerwacji miękkich w rozwiązaniu Supply Chain Management

Można kompensować ilość zarezerwowaną programowo po fizycznym odjęciu ilości z zamówienia w rozwiązaniu Supply Chain Management lub innym systemie ERP. Widoczność zapasów oferuje gotową integrację przesunięcia miękkiej rezerwacji z Supply Chain Management.

Wykonaj poniższe kroki, aby zrównoważyć rezerwację miękką.

1. Zaloguj się do modułu Supply Chain Management.
1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Ponownie utwórz zewnętrzne zamówienie sprzedaży i dodaj wiersz sprzedaży, który używa dokładnie tego samego identyfikatora produktu, organizacji, oddziału, magazynu i wartości wymiarów.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz właśnie wprowadzony wiersz sprzedaży, a następnie na pasku narzędzi wybierz **Inventory \> Rezerwacja** na pasku narzędzi.
1. Wykonaj jeden z następujących kroków:

    - Skopiuj identyfikator rezerwacji soft w odpowiedzi na żądanie rezerwacji programowej i wklej go do **pola Identyfikator rezerwacji**.
    - Pole **Identyfikator rezerwacji** pozostaw puste, ale zaznacz pole wyboru **Automatyczne przeciwstawne konto przeciwstawne usługi zapasów**. System automatycznie określi, który produkt i wymiary produktu mają zostać odsunięte, na podstawie identyfikatora towaru i wartości wymiarów wprowadzonych w wybranym wierszu.

1. Kliknij przycisk **OK**.
1. Gdy ten sam wiersz sprzedaży jest nadal wybrany, fizycznie zarezerwuj zamówioną ilość, wybierając **Zapasy \> Rezerwacja** na pasku narzędzi **Wiersze zamówienia sprzedaży** skróconej karty.
1. Jeśli wcześniej w polu **Modyfikator przeciwstawny rezerwacji** ustawiono wartość *Zarezerwowane*, przesunięcie będzie wyzwalane, gdy wiersz zamówienia ma stan *Rezerwacja fizyczna* lub *Rezerwacja zamówiona*. Zadanie wsadowe jest uruchamiane raz na minutę w celu zsynchronizowania żądań przesunięcia z programu Supply Chain Management z programem widoczność magazynu.

> [!NOTE]
> W przypadku stanów transakcji, które zawierają określony modyfikator kompensacji rezerw, aktualizacja transakcji będzie przeciwstawna do odpowiedniego rekordu rezerwacji, jeśli są spełnione następujące warunki:
>
> - Identyfikator rezerwacji w transakcji magazynowej pasuje do identyfikatora rezerwacji rekordu rezerwacji w usłudze Widoczność magazynu.
> - Wymiary transakcji magazynowej odpowiadają wymiarom rekordu rezerwacji w Widoczności zapasów.
> - Zmiany stanu transakcji magazynowej wyzwalają kompensacje dla rezerwacji, gdy stan transakcji magazynowej odzwierciedla fakt, że proces zamówienia został ukończony lub pominięty.

Ilości kompensowane są zgodne z ilościami zapasów, które są określone w odpowiednich transakcjach magazynowych. Przesunięcie zacznie obowiązywać tylko wtedy, gdy zarezerwowana ilość pozostanie w Widoczności zapasów.

### <a name="cancel-or-revert-a-soft-reservation"></a>Anuluj lub przywróć rezerwację miękką

Jeśli oryginalny wiersz zamówienia zostanie anulowany lub usunięty i musisz cofnąć odpowiednią rezerwację programową, zaksięguj ujemną ilość, która zawiera dokładnie te same informacje w treści zapytania interfejsu API.
