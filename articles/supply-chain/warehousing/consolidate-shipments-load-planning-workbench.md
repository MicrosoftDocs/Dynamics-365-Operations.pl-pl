---
title: Konsolidowanie wysyłek przy użyciu zwalniania do magazynu z pulpitu planowania wysyłki ładunku
description: W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tego samego ładunku, a następnie automatycznie konsolidowanych w ramach wysyłek.
author: GarmMSFT
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
ms.openlocfilehash: b724b3f040a1b277d99dd067525dfda2b47ca73b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577895"
---
# <a name="consolidate-shipments-by-releasing-to-warehouse-from-the-load-planning-workbench"></a>Konsolidowanie wysyłek przy użyciu zwalniania do magazynu z pulpitu planowania wysyłki ładunku

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tego samego ładunku, a następnie automatycznie konsolidowanych w ramach wysyłek.

## <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów

W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy. Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.

## <a name="create-the-sales-orders-for-this-scenario"></a>Tworzenie zamówień sprzedaży dla tego scenariusza

Rozpocznij od utworzenia kolekcji zamówień sprzedaży, z którymi możesz pracować. Musisz pracować z magazynem, w którym włączono obsługę zaawansowanych procesów magazynu (WMS). O ile inny magazyn nie został wyraźnie wskazany, ten sam magazyn musi być używany dla każdego z poniższych zestawów zamówień.

Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz kolekcję zamówień sprzedaży z ustawieniami opisanymi w poniższych podsekcjach.

### <a name="create-order-set-1"></a>Tworzenie zestawu zamówień 1

#### <a name="sales-order-1-1"></a>Zamówienie sprzedaży 1-1

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Metoda dostawy:** *Airwa-Air*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

#### <a name="sales-order-1-2"></a>Zamówienie sprzedaży 1-2

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Metoda dostawy:** *Airwa-Air*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

#### <a name="sales-order-1-3"></a>Zamówienie sprzedaży 1-3

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Metoda dostawy:** *10*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.
1. Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0002* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*
    - **Metoda dostawy:** *Airwa-Air*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować drugi wiersz zamówienia.

### <a name="create-order-set-2"></a>Tworzenie zestawu zamówień 2

#### <a name="sales-orders-2-1-and-2-2"></a>Zamówienia sprzedaży 2-1 i 2-2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-002*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.
1. Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)
    - **Ilość:** *1.00*
    - **Metoda dostawy:** *Airwa-Air*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować drugi wiersz zamówienia.

### <a name="create-order-set-3"></a>Tworzenie zestawu zamówień 3

#### <a name="sales-orders-3-1-and-3-2"></a>Zamówienia sprzedaży 3-1 i 3-2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Zapotrzebowanie odbiorcy:** *1*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

#### <a name="sales-orders-3-3-and-3-4"></a>Zamówienia sprzedaży 3-3 i 3-4

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Zapotrzebowanie odbiorcy:** *2*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

### <a name="create-order-set-4"></a>Tworzenie zestawu zamówień 4

#### <a name="sales-orders-4-1-and-4-2"></a>Zamówienia sprzedaży 4-1 i 4-2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-003*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

#### <a name="sales-orders-4-3-and-4-4"></a>Zamówienia sprzedaży 4-3 i 4-4

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-004*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

#### <a name="sales-orders-4-5-and-4-6"></a>Zamówienia sprzedaży 4-5 i 4-6

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-007*
    - **Oddział:** *6*
    - **Magazyn:** *61*
    - **Pula:** *ShipCons*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

#### <a name="sales-orders-4-7-and-4-8"></a>Zamówienia sprzedaży 4-7 i 4-8

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-007*
    - **Oddział:** *6*
    - **Magazyn:** *61*
    - **Pula:** pozostaw to pole puste.

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a>Tworzenie ładunków i zwalnianie ich do magazynu przy użyciu pulpitu planowania wysyłki ładunku

Wykonaj poniższe kroki, aby utworzyć ładunek dla każdego zestawu zamówień utworzonego dla tego scenariusza, a następnie zwolnić go do magazynu.

1. Wybierz kolejno pozycje **Zarządzanie magazynem \> Ładunki \> Pulpit planowania wysyłki ładunku**.
1. Na karcie **Wiersze sprzedaży** znajdź i wybierz wszystkie wiersze zamówienia sprzedaży w jednym z zestawów zamówień utworzonych dla tego scenariusza.
1. W okienku akcji na karcie **Popyt i podaż** wybierz pozycję **Dodaj \> Do nowego ładunku**, aby dodać wybrane wiersze zamówienia do nowego ładunku.
1. W oknie dialogowym **Przypisanie szablonu ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon ładunku, na przykład *Standardowy szablon ładunku*.
1. Kliknij przycisk **OK**, aby zamknąć okno dialogowe. 
1. W sekcji **Ładunki** znajdź i wybierz właśnie utworzony ładunek.
1. Wybierz pozycję **Zwolnij \> Zwolnij do magazynu**, aby zwolnić wybrany ładunek do magazynu.
1. Powtórz tę procedurę dla trzech pozostałych zestawów zamówień utworzonych dla tego scenariusza.

## <a name="verify-the-shipments"></a>Weryfikowanie wysyłek

Poniższa procedura umożliwia zweryfikowanie, czy wysyłki zostały utworzone lub zaktualizowane w wyniku konsolidacji wysyłki. Przy jej użyciu można przejrzeć wszystkie zestawy zamówień utworzone dla tego scenariusza, a następnie przejrzeć kolejne podsekcje, aby upewnić się, że otrzymano oczekiwane wyniki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Znajdź i wybierz wymaganą wysyłkę.
1. Jeśli podczas tworzenia lub aktualizowania wysyłki użyto zasad konsolidacji, powinny być one widoczne w polu **Zasady konsolidacji wysyłki**.

### <a name="release-order-set-1-in-one-load"></a>Zwalnianie zestawu zamówień 1 w jednym ładunku

Powinny zostać utworzone dwie następujące wysyłki:

- Pierwsza wysyłka zawiera trzy wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerMode*.
- Druga wysyłka, która nie korzysta z metody dostawy *Trasy lotnicze*, została utworzona przy użyciu zasad konsolidacji wysyłki *CustomerOrderNo*.

### <a name="release-order-set-2-in-one-load"></a>Zwalnianie zestawu zamówień 2 w jednym ładunku

Powinny zostać utworzone trzy następujące wysyłki:

- Pierwsza wysyłka zawiera pozycję typu *Łatwopalne*.
- Każda z dwóch pozostałych wysyłek zawiera jeden wiersz pozycji typu *Materiały wybuchowe*.

### <a name="release-order-set-3-in-one-load"></a>Zwalnianie zestawu zamówień 3 w jednym ładunku

Powinny zostać utworzone dwie następujące wysyłki:

- Pierwsza wysyłka zawiera wiersze zamówienia z zamówienia sprzedaży, w którym pole **Zapotrzebowanie odbiorcy** zostało ustawione na wartość *1*.
- Druga wysyłka zawiera wiersze zamówienia z zamówienia sprzedaży, w którym pole **Zapotrzebowanie odbiorcy** zostało ustawione na wartość *2*.

### <a name="release-order-set-4-in-one-load"></a>Zwalnianie zestawu zamówień 4 w jednym ładunku

Powinny zostać utworzone cztery następujące wysyłki:

- Wiersze z dwóch zamówień dla konta odbiorcy *US-003* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.
- Wiersze z dwóch zamówień dla konta odbiorcy *US-004* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.
- Wiersze z zamówień sprzedaży 4-5 i 4-6 dla konta odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *Pula zamówień*.
- Wiersze z zamówień sprzedaży 4-7 i 4-8 dla konta odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *CrossOrder*.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zasady konsolidacji wysyłki](about-shipment-consolidation-policies.md)
- [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]