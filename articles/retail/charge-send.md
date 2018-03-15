---
title: "Wysyłanie zamówienia z innego sklepu"
description: "W tym temacie opisano funkcję Wysyłanie opłaty."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 797058bdbbdb63a08eb35034ffe3c913307f38df
ms.openlocfilehash: 41434614b01f9a00f2b8a56765ecb90ee07e3d90
ms.contentlocale: pl-pl
ms.lasthandoff: 03/06/2018

---

# <a name="ship-an-order-from-a-different-store"></a>Wysyłanie zamówienia z innego sklepu

[!include[banner](includes/banner.md)]

Funkcja Wysyłanie opłaty w rozwiązaniu Dynamics 365 for Retail umożliwia złożenie zamówień odbiorców w jednym sklepie i wysłanie ich z innego sklepu. Zamówienia odbiorców w kliencie punktu sprzedaży obsługują różne opcje realizacji. Przykłady opcji realizacji:
-   Odbiór z tego samego sklepu w innym dniu.
-   Odbiór z innego sklepu w tym samym lub innym dniu.
-   Wysyłka do domyślnego magazynu wysyłki przypisanego do sklepu i dostawa w określonym dniu.

Funkcja Wysyłanie opłaty wykorzystuje następujące operacje punktu sprzedaży: Wyślij wszystkie produkty i Wyślij zaznaczone produkty. Umożliwia to pracownikowi sklepu wybranie lokalizacji „wyślij z”, z której można zrealizować zamówienie lub wiersz zamówienia. Domyślnie lokalizacja „wyślij z” to magazyn wysyłki skojarzony ze sklepem. Jednakże pracownik sklepu może zmienić tę lokalizację i wybrać dowolny sklep zdefiniowany w grupie lokalizatora sklepów przypisanej do sklepu. 

Możliwość wyboru adresów „wyślij do” pozostaje bez zmian. 

Metody wysyłki, których można użyć do realizacji wiersza zamówienia są oparte na konfiguracji prawidłowych trybów dostawy produktów i adresów. Ponieważ reguły dotyczące prawidłowych trybów dostawy są obsługiwane tylko w Centrali sieci sprzedaży (HQ), klient punktu sprzedaży wykonuje wywołanie w czasie rzeczywistym, aby pobrać prawidłowe tryby dostawy dla wiersza wysyłki. 


