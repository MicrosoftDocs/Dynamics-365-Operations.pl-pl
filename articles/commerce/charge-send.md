---
title: Wysyłka zamówień z innego sklepu za pomocą funkcji Wysyłanie opłaty
description: W tym temacie opisano funkcję Wysyłanie opłaty.
author: ashishmsft
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: b9e0c4f55fd823bf7471edfe6ce1d424b0179d21
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800478"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Wysyłka zamówień z innego sklepu za pomocą funkcji Wysyłanie opłaty

[!include [banner](includes/banner.md)]

Funkcja Wysyłanie opłaty w rozwiązaniu Commerce umożliwia złożenie zamówień odbiorców w jednym sklepie i wysłanie ich z innego sklepu.

Zamówienia odbiorców w kliencie punktu sprzedaży obsługują różne opcje realizacji. Przykłady opcji realizacji:

- Odbiór z tego samego sklepu w innym dniu.
- Odbiór z innego sklepu w tym samym lub innym dniu.
- Wysyłka do domyślnego magazynu wysyłki przypisanego do sklepu i dostawa w określonym dniu.

Funkcja Wysyłanie opłaty wykorzystuje następujące operacje punktu sprzedaży: Wyślij wszystkie produkty i Wyślij zaznaczone produkty. Umożliwia to pracownikowi sklepu wybranie lokalizacji „wyślij z”, z której można zrealizować zamówienie lub wiersz zamówienia. Domyślnie lokalizacja „wyślij z” to magazyn wysyłki skojarzony ze sklepem. Jednakże pracownik sklepu może zmienić tę lokalizację i wybrać dowolny sklep zdefiniowany w grupie lokalizatora sklepów przypisanej do sklepu.

Możliwość wyboru adresów „wyślij do” pozostaje bez zmian.

Metody wysyłki, których można użyć do realizacji wiersza zamówienia są oparte na konfiguracji prawidłowych trybów dostawy produktów i adresów. Ponieważ reguły dotyczące prawidłowych trybów dostawy są obsługiwane tylko w Headquarters (HQ), klient punktu sprzedaży wykonuje wywołanie w czasie rzeczywistym, aby pobrać prawidłowe tryby dostawy dla wiersza wysyłki.


[!INCLUDE[footer-include](../includes/footer-banner.md)]