---
title: Konsolidowanie wysyłek podczas zwalniania ich do magazynu przy użyciu automatycznego zwalniania zamówień sprzedaży
description: W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tej samej zautomatyzowanej okresowej procedury zwalniania do magazynu.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: f4d095456435a3401daa173d79b80b81176a3c17
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987125"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a>Konsolidowanie wysyłek podczas zwalniania ich do magazynu przy użyciu automatycznego zwalniania zamówień sprzedaży

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono scenariusz, w którym wiele zamówień jest zwalnianych do magazynu w ramach tej samej zautomatyzowanej okresowej procedury zwalniania do magazynu. Zamówienia będą automatycznie konsolidowane w wysyłki na podstawie reguł zdefiniowanych jako zasady konsolidacji wysyłki.

W tym scenariuszu utworzysz zestawy zamówień sprzedaży i zwolnisz poszczególne zestawy do magazynu. Następnie przejrzysz wysyłki utworzone lub zaktualizowane podczas konsolidowania wysyłki na podstawie skonfigurowanych zasad.

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

#### <a name="sales-order-1-2"></a>Zamówienie sprzedaży 1-2

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Metoda dostawy:** *Airwa-Air*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

#### <a name="sales-order-1-3"></a>Zamówienie sprzedaży 1-3

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Metoda dostawy:** *10*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0002* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*
    - **Metoda dostawy:** *Airwa-Air*

### <a name="create-order-set-2"></a>Tworzenie zestawu zamówień 2

#### <a name="sales-orders-2-1-and-2-2"></a>Zamówienia sprzedaży 2-1 i 2-2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-002*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)
    - **Ilość:** *1.00*

1. Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)
    - **Ilość:** *1.00*
    - **Metoda dostawy:** *Airwa-Air*

### <a name="create-order-set-3"></a>Tworzenie zestawu zamówień 3

#### <a name="sales-order-3-1"></a>Zamówienie sprzedaży 3-1

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-002*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *M9200* (pozycja, dla której filtr **Kod 4** został ustawiony na *Łatwopalne*)
    - **Ilość:** *1.00*

1. Dodaj drugi wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *M9201* (pozycja, dla której filtr **Kod 4** został ustawiony na *Materiały wybuchowe*)
    - **Ilość:** *1.00*
    - **Metoda dostawy:** *Airwa-Air*

> [!NOTE]
> To zamówienie jest identyczne jak dwa zamówienia utworzone dla zestawu zamówień 2. Jest ono jednak wymienione jako oddzielny zestaw zamówień, ponieważ w tym scenariuszu zostanie zwolnione osobno w późniejszym czasie.

### <a name="create-order-set-4"></a>Tworzenie zestawu zamówień 4

#### <a name="sales-order-4-1"></a>Zamówienie sprzedaży 4-1

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Zapotrzebowanie odbiorcy:** *1*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

### <a name="create-order-set-5"></a>Tworzenie zestawu zamówień 5

#### <a name="sales-orders-5-1-and-5-2"></a>Zamówienia sprzedaży 5-1 i 5-2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Zapotrzebowanie odbiorcy:** *2*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

#### <a name="sales-order-5-3"></a>Zamówienie sprzedaży 5-3

1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Zapotrzebowanie odbiorcy:** *1*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

### <a name="create-order-set-6"></a>Tworzenie zestawu zamówień 6

#### <a name="sales-orders-6-1-and-6-2"></a>Zamówienia sprzedaży 6-1 i 6-2

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-003*
    - **Zapotrzebowanie odbiorcy:** *2*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>Zamówienia sprzedaży 6-3 i 6-4

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-004*
    - **Zapotrzebowanie odbiorcy:** *1*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>Zamówienia sprzedaży 6-5 i 6-6

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-007*
    - **Oddział:** *6*
    - **Magazyn:** *61*
    - **Pula:** *ShipCons*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>Zamówienia sprzedaży 6-7 i 6-8

1. Utwórz dwa identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-007*
    - **Oddział:** *6*
    - **Magazyn:** *61*
    - **Pula:** pozostaw to pole puste.

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Automatyczne zwalnianie zamówień sprzedaży do magazynu

Dla każdego utworzonego wcześniej zestawu zamówień sprzedaży zostanie wykonana procedura automatycznego zwalniania do magazynu. W każdym przypadku będziesz korzystać z [podstawowej procedury zwalniania do magazynu](#release-procedure), opisanej w tym miejscu.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Podstawowa procedura zwalniania do magazynu

Dla każdego utworzonego wcześniej zestawu zamówień sprzedaży wykonasz trzy procedury opisane w poniższych podsekcjach.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>Aktualizowanie szablonu grupy czynności, który będzie używany podczas zwalniania

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. Ustaw pole **Typ szablonu grupy czynności** na *Wysyłka*.
1. Znajdź i wybierz szablon grupy czynności skojarzony z magazynem, który został użyty w zestawach zamówień utworzonych dla tego scenariusza. Jeśli na przykład użyto magazynu *24*, wybierz szablon grupy czynności **24 — wysyłka domyślna**. Jeśli użyto magazynu *61*, wybierz szablon grupy czynności **61 — wysyłka**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. Ustaw opcję **Przetwarza grupę czynności w czasie uwalniania jej do magazynu** na wartość *Nie*.

#### <a name="release-to-the-warehouse"></a>Zwalnianie do magazynu

1. Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Automatyczne zwalnianie zamówień sprzedaży**
1. Ustaw pole **Ilość do zwolnienia** na wartość *Wszystko*.
1. Na skróconej karcie **Rekordy do uwzględnienia** wybierz pozycję **Filtr**, aby otworzyć okno dialogowe zapytania.
1. Na karcie **Zakres** wybierz przycisk **Dodaj**, aby dodać wiersz zawierający następujące ustawienia do siatki:

    - **Tabela:** *Zamówienie sprzedaży*
    - **Tabela pochodna:** *Zamówienie sprzedaży*
    - **Pole:** *Zamówienie sprzedaży*
    - **Kryteria:** wprowadź rozdzielaną przecinkami listę numerów zamówień sprzedaży z żądanego zestawu zamówień.

1. Wybierz przycisk **OK**, aby zapisać zapytanie.
1. Wybierz przycisk **OK**, aby rozpocząć procedurę *automatycznego zwalniania do magazynu*.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>Przeglądanie utworzonej lub zaktualizowanej wysyłki

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Znajdź i wybierz wymaganą wysyłkę.
1. Jeśli podczas tworzenia lub aktualizowania wysyłki użyto zasad konsolidacji, powinny być one widoczne w polu **Zasady konsolidacji wysyłki**.

### <a name="release-sales-orders-from-order-set-1"></a>Zwalnianie zamówień sprzedaży z zestawu zamówień 1

Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 1.

Po zakończeniu powinny być widoczne dwie utworzone wysyłki:

- Pierwsza wysyłka zawiera trzy wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerMode*.
- Druga wysyłka, która nie korzysta z metody dostawy *Trasy lotnicze*, została utworzona przy użyciu zasad konsolidacji wysyłki *CustomerOrderNo*.

### <a name="release-sales-orders-from-order-set-2"></a>Zwalnianie zamówień sprzedaży z zestawu zamówień 2

Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 2.

Po zakończeniu powinny być widoczne trzy utworzone wysyłki:

- Pierwsza wysyłka zawiera pozycję typu *Łatwopalne*.
- Każda z dwóch pozostałych wysyłek zawiera jeden wiersz pozycji typu *Materiały wybuchowe*.

### <a name="release-sales-orders-from-order-set-3"></a>Zwalnianie zamówień sprzedaży z zestawu zamówień 3

Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 3.

Po zakończeniu powinny być widoczne następujące wykonane akcje:

- Zaktualizowano jedną istniejącą wysyłkę (wysyłkę utworzoną po zwolnieniu zestawu zamówień 2 do magazynu). Dodano wiersz z pozycją typu *Łatwopalne*.
- Utworzono jedną nową wysyłkę zawierającą pozycję typu *Materiały wybuchowe*.

### <a name="release-sales-orders-from-order-set-4"></a>Zwalnianie zamówień sprzedaży z zestawu zamówień 4

Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 4.

Po zakończeniu powinna być widoczna jedna zaktualizowana istniejąca wysyłka (w której pole **Zapotrzebowanie odbiorcy** ma wartość *1*). Dodano do niej jeden nowy wiersz.

### <a name="release-sales-orders-from-order-set-5"></a>Zwalnianie zamówień sprzedaży z zestawu zamówień 5

Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 5.

Po zakończeniu powinny być widoczne następujące wykonane akcje:

- Zaktualizowano jedną istniejącą wysyłkę (w której pole **Zapotrzebowanie odbiorcy** ma wartość *1*). Dodano do niej wiersz z zamówienia sprzedaży 5-3 (w którym pole **Zapotrzebowanie odbiorcy** ma wartość *1*).
- Utworzono jedną nową wysyłkę, w której wiersze z zamówień sprzedaży 5-1 i 5-2 są pogrupowane w ramach jednej wysyłki.

### <a name="release-sales-orders-from-order-set-6"></a>Zwalnianie zamówień sprzedaży z zestawu zamówień 6

Wykonaj kroki [podstawowej procedury zwalniania do magazynu](#release-procedure), aby zwolnić zamówienia sprzedaży z zestawu zamówień 6.

Po zakończeniu powinny być widoczne cztery utworzone wysyłki:

- Wiersze z dwóch zamówień dla odbiorcy *US-003* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.
- Wiersze z dwóch zamówień dla odbiorcy *US-004* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji wysyłki *Pula zamówień*.
- Wiersze z zamówień sprzedaży 6-5 i 6-6 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *Pula zamówień*.
- Wiersze z zamówień sprzedaży 6-7 i 6-8 dla odbiorcy *US-007* zostały zgrupowane w jednej wysyłce przy użyciu zasad konsolidacji *CrossOrder*.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zasady konsolidacji wysyłki](about-shipment-consolidation-policies.md)
- [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md)
