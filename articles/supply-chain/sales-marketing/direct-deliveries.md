---
title: Dostawy bezpośrednie
description: Ten artykuł zawiera informacje dotyczące dostaw bezpośrednich. Dostawy bezpośrednie to dostawy wysyłane bezpośrednio od dostawcy do odbiorców końcowych.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchCreateFromSalesOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 9704
ms.assetid: 64c51384-8a4e-45d0-83c1-12cea22902f9
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7dd562a67f891c6943db00a6f8cf514bec19677
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572584"
---
# <a name="direct-deliveries"></a>Dostawy bezpośrednie

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje dotyczące dostaw bezpośrednich. Dostawy bezpośrednie to dostawy wysyłane bezpośrednio od dostawcy do odbiorców końcowych.

Bezpośrednie dostawy pozwalają zaoszczędzić czas i koszty magazynowania, ponieważ produktów nie przechowuje się we własnym magazynie przed wysłaniem do odbiorcy.  

Dostawy bezpośrednie można tworzyć na stronie **Zamówienie sprzedaży**. Najpierw trzeba utworzyć zamówienie sprzedaży i wiersze zamówienia. Następnie, w okienku akcji, na karcie **Zamówienia sprzedaży** wybierz **Dostawa bezpośrednia**. Na końcu określ wiersze, które muszą być traktowane jako dostawa bezpośrednia. Powoduje to utworzenie łącza między wierszami zamówienia sprzedaży z dostawą bezpośrednią a odpowiednimi wierszami zamówienia zakupu.  

**Uwaga:** Jeśli część zamówionej ilości została dostarczona, należy podzielić pozostałą ilości. Utwórz nowy wiersz z ilością, która musi być dostarczone bezpośrednio i odejmij tę ilość od ilości w pierwotnym wierszu. Na przykład, jeśli ilość oryginalna wynosiła 15 i pięć produktów zostało dostarczonych, należy utworzyć nowy wiersz na pozostałą ilość równą 10, a następnie zmniejszyć ilość oryginalną o tę kwotę.  

Gdy zostanie utworzone łącze dostawy bezpośredniej między wierszami zamówienia sprzedaży a wierszami zamówienia zakupu, można zaktualizować dokument dostawy dla zamówienia sprzedaży przy użyciu dokumentu dostawy. Uruchom aktualizację dokumentu dostawy lub aktualizację faktury z zamówienia zakupu. Aktualizacja faktury zamówienia sprzedaży musi być przeprowadzona ze strony **Zamówienie sprzedaży**. Aktualizacja faktury nie może powodować, że ilość na zamówieniu sprzedaży jest większa niż ilość, która została zarejestrowana jako otrzymana. Na przykład wiersz zamówienia sprzedaży zawiera 10 sztuk, ale tylko 5 sztuk z wiersza zamówienia sprzedaży zostało zaktualizowane za pomocą dokumentu dostawy. Wybranie opcji **Wszystko** na liście **Ilość** podczas fakturowania aktualizacji zamówienia sprzedaży powoduje, że tylko te towary, które zostały odebrane, lub zaktualizowane za pomocą dokumentu dostawy, są zaktualizowane na fakturze. Cały wiersz zamówienia sprzedaży nie zostanie zaktualizowany.

## <a name="delivery-date"></a>Data dostawy
Aktualizacja pola **Żądana data przyjęcia** w wierszu zamówienia sprzedaży w polu **Data dostawy** w odpowiednim wierszu zamówienia zakupu. Podobnie aktualizacja pola **Potwierdzone** w wierszu zamówienia zakupu powoduje także aktualizację pól **Potwierdzona data odbioru** i **Potwierdzona data wysyłki** w odpowiednim wierszu zamówienia sprzedaży.

## <a name="delivery-address"></a>Adres dostawy
Zazwyczaj adresem dostawy zamówienia zakupu jest adres firmy. Jednak podczas tworzenia dostawy bezpośredniej jako adres dostawy jest wprowadzany adres odbiorcy. Zmiana adresu dostawy dla wiersza zamówienia zakupu o typie **Dostawa bezpośrednia** spowoduje również aktualizację adresu dostawy w odpowiednim wierszu zamówienia sprzedaży. Podobnie zmiana adresu dostawy w wierszu zamówienia sprzedaży spowoduje również aktualizację adresu dostawy w wierszu zamówienia zakupu.

## <a name="deleting-order-lines"></a>Usuwanie wierszy zamówienia
W przypadku usuwania wiersza zamówienia sprzedaży o typie **Dostawa bezpośrednia** wyświetlane jest ostrzeżenie z informacją, że do tego wiersza są dołączone wiersze zamówienia zakupu. Jeśli wiersz zamówienia sprzedaży został częściowo dostarczony, nie można usunąć tego wiersza zamówienia sprzedaży ani dołączonych do niego wierszy zamówienia zakupu.

## <a name="warehouse"></a>Magazyn
Podczas tworzenia dostawy bezpośredniej, sprzedawane towary nigdy faktycznie nie docierają do magazynu. Niemniej jednak nadal należy określić magazyn w wierszu zamówienia sprzedaży. Podobnie wymagane pobrania mogą być określone w grupie modeli towaru dla towaru. Jednakże ponieważ towary nigdy faktycznie nie docierają do magazynu, wymagania te są ignorowane, gdy zamówienie sprzedaży jest dostawą bezpośrednią.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]