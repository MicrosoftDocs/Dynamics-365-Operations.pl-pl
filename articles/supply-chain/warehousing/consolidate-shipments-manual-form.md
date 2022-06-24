---
title: Ręczne konsolidowanie wysyłek przy użyciu strony konsolidacji wysyłek
description: W tym artykule przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu, a później konsolidowanych przy użyciu strony konsolidowania wysyłek.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: d24542a126d64621525f62e694bbc7174b474810
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897350"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Ręczne konsolidowanie wysyłek przy użyciu strony konsolidacji wysyłek

[!include [banner](../includes/banner.md)]

W tym artykule przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu, a później konsolidowanych przy użyciu strony **konsolidowania wysyłek**.

## <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Każdy scenariusz w tym artykule zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów

W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy. Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.

## <a name="create-the-sales-orders-for-this-scenario"></a>Tworzenie zamówień sprzedaży dla tego scenariusza

Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować. Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS). O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.

Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.

### <a name="create-sales-orders-1-and-2"></a>Tworzenie zamówień sprzedaży 1 i 2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-007*
    - **Pula:** *ShipCons*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

### <a name="create-sales-orders-3-and-4"></a>Tworzenie zamówień sprzedaży 3 i 4

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-007*
    - **Pula:** pozostaw to pole puste.

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

## <a name="release-the-orders-to-the-warehouse"></a>Zwalnianie zamówień do magazynu

Wykonaj poniższe kroki, aby zwolnić każde zamówienie sprzedaży utworzone dla tego scenariusza do magazynu.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży**.
1. Znajdź i zaznacz zamówienie sprzedaży do zwolnienia.
1. W okienku akcji na karcie **Magazyn** wybierz pozycję **Akcje \> Zwolnij do magazynu**, aby zwolnić wybrane zamówienie sprzedaży.
1. Powtórz tę procedurę dla wszystkich zamówień sprzedaży utworzonych dla tego scenariusza.

## <a name="consolidate-shipments"></a>Konsoliduj wysyłki

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Znajdź i wybierz wysyłkę, która została utworzona, gdy zamówienie sprzedaży 1 zostało zwolnione do magazynu. (Odpowiednie pole **Zasady konsolidacji wysyłki** powinno być ustawione na wartość *Pula zamówień*).
1. W okienku akcji na karcie **Wysyłki** wybierz pozycję **Wysyłki \> Konsoliduj wysyłki**.
1. Zweryfikuj wysyłki sugerowane do konsolidacji. Tylko jedna wysyłka mająca takie same zasady powinna być sugerowana do konsolidacji.
1. Zamknij stronę **Zasady konsolidacji wysyłki**.
1. Znajdź i wybierz wysyłkę, która została utworzona, gdy zamówienie sprzedaży 3 zostało zwolnione do magazynu. (Odpowiednie pole **Zasady konsolidacji wysyłki** powinno być ustawione na wartość *Domyślne*).
1. W okienku akcji na karcie **Wysyłki** wybierz pozycję **Wysyłki \> Konsoliduj wysyłki**.
1. Upewnij się, że nie wybrano wysyłek sugerowanych do konsolidacji.
1. Wybierz pozycję **Pokaż filtry**.
1. W okienku **Filtry** usuń filtr **Numer zamówienia**, a następnie wybierz przycisk **Zastosuj**.
1. Zweryfikuj wysyłki sugerowane do konsolidacji. Tylko jedna wysyłka mająca takie same zasady powinna być sugerowana do konsolidacji.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zasady konsolidacji wysyłki](about-shipment-consolidation-policies.md)
- [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]