---
title: Konsolidowanie wysyłek, gdy zasady konsolidacji wysyłki są zastąpione na stronie zwalniania do magazynu
description: W tym temacie przedstawiono scenariusz, w którym co najmniej jeden wiersz sprzedaży musi zostać ręcznie zwolniony do magazynu z poziomu strony zwalniania do magazynu, a zasady konsolidacji wysyłki zdefiniowane w systemie muszą zostać zastąpione przed zwolnieniem.
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
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 406ff268eede4a9d448b3b9c1729a00fcec8f21e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986751"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a>Konsolidowanie wysyłek, gdy zasady konsolidacji wysyłki są zastąpione na stronie zwalniania do magazynu

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono scenariusz, w którym co najmniej jeden wiersz sprzedaży musi zostać ręcznie zwolniony do magazynu z poziomu strony **zwalniania do magazynu**, a zasady konsolidacji wysyłki zdefiniowane w systemie muszą zostać zastąpione przed zwolnieniem. Zastąpienie zasady konsolidacji wysyłki może być wymagane, jeśli na przykład zamówienie, które nie jest zwykle skonsolidowane w przypadku otwartych wysyłek, musi zostać skonsolidowane z otwartymi wysyłkami.

W trakcie tego scenariusza utworzysz zestaw zamówień sprzedaży, a następnie zastąpi domyślne zasady konsolidacji wysyłki przed zwolnieniem zamówień do magazynu.

## <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

Każdy scenariusz w tym temacie zawiera odwołania do wartości i rekordów uwzględnionych w standardowych danych pokazu dostępnych dla rozwiązania Microsoft Dynamics 365 Supply Chain Management. Aby użyć wartości określonych w tym miejscu podczas wykonywania ćwiczeń, upewnij się, że praca odbywa się w środowisku, w którym są zainstalowane dane demonstracyjne, i przed rozpoczęciem ustaw firmę na **USMF**.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Konfigurowanie zasad konsolidacji wysyłki i filtrów produktów

W opisanym poniżej scenariuszu przyjęto założenie, że użytkownik już włączył funkcję, wykonał ćwiczenia z tematu [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md) i utworzył zasady oraz inne opisane w nim rekordy. Przed kontynuowaniem tego scenariusza pamiętaj o wykonaniu poniższych ćwiczeń.

## <a name="create-the-sales-orders-for-this-scenario"></a>Tworzenie zamówień sprzedaży dla tego scenariusza

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia sprzedaży** i utwórz trzy identyczne zamówienia sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-002*

1. Dodaj wiersz zamówienia sprzedaży z następującymi ustawieniami:

    - **Kod pozycji:** *A0001* (pozycja, do której nie przypisano filtru **Kod 4**)
    - **Ilość:** *1.00*

1. Wybierz pozycję **Zapasy \> Rezerwacja**, a następnie w okienku akcji wybierz pozycję **Rezerwacja partii**, aby zarezerwować wiersz zamówienia.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Zwalnianie zamówień sprzedaży ze strony zwalniania do magazynu

Wykonać poniższe kroki, aby zastępować zasady konsolidacji wysyłki podczas zwalniania do magazynu.

1. Przejdź do pozycji **Zarządzanie magazynem \> Zwolnij do magazynu \> Zwolnij do magazynu**.
1. W górnym okienku wybierz pierwsze zamówienie sprzedaży utworzone dla tego scenariusza.
1. Wybierz przycisk **Dodaj**, aby dodać wiersz do zwolnienia do magazynu. Zauważ, że *domyślne* zasady konsolidacji wysyłki są stosowane w dolnym okienku.
1. W dolnym okienku wybierz pozycję **Wybierz nowe zasady konsolidacji wysyłki**.
1. Wybierz zasady umożliwiające konsolidację z innymi otwartymi wysyłkami tych samych zasad. Na przykład wybierz zasady *CustomerOrderNo*.
1. Wybierz pozycję **Zwolnij do magazynu**.
1. Wybierz drugie i trzecie zamówienie sprzedaży utworzone dla tego scenariusza.
1. Wybierz przycisk **Dodaj**, aby dodać wiersze do zwolnienia do magazynu. Zauważ, że *domyślne* zasady są stosowane w dolnym okienku.
1. Wybierz drugi wiersz, a następnie w polu **Wybierz nowe zasady konsolidacji wysyłki** wybierz zasady *CustomerOrderNo*.
1. Wybierz pozycję **Zwolnij do magazynu** dla obu wierszy.

## <a name="verify-the-shipments"></a>Weryfikowanie wysyłek

Powinny zostać utworzone dwie następujące wysyłki:

- Pierwsza wysyłka zawiera dwa wiersze i została utworzona za pomocą zasad konsolidacji wysyłki *CustomerOrderNo*.
- Druga wysyłka zawiera jeden wiersz i została utworzona za pomocą zasad konsolidacji wysyłki *Domyślne*.

Aby przejrzeć utworzone wysyłki, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Znajdź i wybierz wymaganą wysyłkę.
1. W polu **Zasady konsolidacji wysyłki** przejrzyj zasady konsolidacji, które zostały użyte podczas tworzenia wysyłki.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Zasady konsolidacji wysyłki](about-shipment-consolidation-policies.md)
- [Konfigurowanie zasad konsolidacji wysyłki](configure-shipment-consolidation-policies.md)
