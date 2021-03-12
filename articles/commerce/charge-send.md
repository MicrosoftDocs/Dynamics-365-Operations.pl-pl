---
title: Wysyłka zamówień z innego sklepu za pomocą funkcji Wysyłanie opłaty
description: W tym temacie opisano funkcję Wysyłanie opłaty.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: d8c2288a18398f71a75dad6e51d51ba4b09561e6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997682"
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
