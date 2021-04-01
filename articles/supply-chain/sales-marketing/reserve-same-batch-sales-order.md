---
title: Rezerwowanie takiej samej partii na potrzeby zamówienia sprzedaży
description: Ten artykuł przedstawia sposób konfigurowania produktu w celu umożliwienia rezerwacji zapasów z jednej partii zapasów.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c7745b1306142678760318cc47f54b93d6f727a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231823"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Rezerwowanie takiej samej partii na potrzeby zamówienia sprzedaży

[!include [banner](../includes/banner.md)]

Ten artykuł przedstawia sposób konfigurowania produktu w celu umożliwienia rezerwacji zapasów z jednej partii zapasów.

Rezerwacja tej samej partii umożliwia rezerwowanie zapasu dla wiersza zamówienia sprzedaży z jednej partii zapasów. Na przykład klient zamawiający tapety może zażądać, by całe zamówienie zawierało towar z jednej partii, aby uniknąć różnic między rolkami. Aby skonfigurować produktu do użycia rezerwacji tej samej partii, w grupie modeli towaru, grupie wymiarów śledzenia i grupie wymiarów magazynowania muszą być aktywne następujące ustawienia przypisane do produktu:

- **Grupy modeli towarów** — grupa musi mieć zaznaczone pola **Wybór tej samej partii** i **Konsoliduj zapotrzebowanie** w grupie pól **rezerwacji** dla zasad zapasów.
- **Grupy wymiarów śledzenia** — grupa mieć zaznaczone pole **plan zapotrzebowania wg wymiaru** dla numeru partii.
- **Grupy wymiarów magazynowania** — grupa musi mieć zaznaczone pole **plan zapotrzebowania wg wymiaru** dla opcji **Oddział** i **Magazyn**.

Podczas rezerwowania zapasów produktu w wierszu zamówienia sprzedaży, dla którego zdefiniowano dla wybór tej samej partii, system próbuje zarezerwować zamówioną ilość z jednej partii zapasów. Uwzględnione są również wszelkie specyficzne wymagania atrybutów partii. Jeśli w pojedynczej partii nie ma wystarczającej ilości towaru, zostanie wyświetlona strona **Konflikt rezerwacji tej samej partii**. Na tej stronie opisano problemy, a także akcje, które należy wykonać, aby kontynuować wykonywanie rezerwacji. Następujące warunki mogą uniemożliwić zarezerwowane partii:

- Dla kodu dyspozycji partii jest zaznaczona opcja **Blokuj rezerwację** dla sprzedaży oznaczonych jako **zablokowano**.
- Partia wygasła, na podstawie daty ważności oraz jakiekolwiek dni możliwej sprzedaży. Element nadal można uznać za do rezerwacji, jeśli grupa modeli pozycji dla towaru jest ewidencjonowana według zasady FEFO, a okres przydatności jest kryterium pobrania.
- Partia nie ma wystarczającej liczby pozostałych dni przydatności (według daty ważności, daty przydatności i liczby dni możliwej sprzedaży u odbiorcy).

W przypadku towarów skojarzonych z grupą wymiarów magazynowania, w której jest włączona opcja **Używaj procesów zarządzania magazynem**, można zarezerwować określone numery partii przy użyciu hierarchii rezerwacji o wymiarze magazynowym numer partii zdefiniowanym powyżej wymiaru lokalizacji. Strona **Rezerwacja partii** dla wierszy sprzedaży i zamówień przeniesienia umożliwia również wybranie i zarezerwowanie wielu wierszy na podstawie dostępnych numerów partii. Aby uzyskać więcej informacji na temat czynności, które należy wykonać w przypadku korzystania z hierarchii rezerwacji z wymiarem numeru partii poniżej lokalizacji, należy zapoznać się z tematem [Elastyczne zasady rezerwacji wymiarów na poziomie magazynu](../warehousing/flexible-warehouse-level-dimension-reservation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]