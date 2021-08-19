---
title: Harmonogramy dostaw
description: Harmonogramy dostaw umożliwiają śledzenie ilości w wierszu zamówienia, gdy jest używanych wiele dostaw dla jednego zamówienia sprzedaży, oferty sprzedaży lub zamówienia zakupu.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b9d7636a9a246b069fbd419d1d857ca47c73ff6ddd9b620f077b0ab15c23c67
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721278"
---
# <a name="delivery-schedules"></a>Harmonogramy dostaw

[!include [banner](../includes/banner.md)]

Harmonogramy dostaw umożliwiają śledzenie ilości w wierszu zamówienia, gdy jest używanych wiele dostaw dla jednego zamówienia sprzedaży, oferty sprzedaży lub zamówienia zakupu.

Harmonogramu dostaw używa się, gdy łączna ilość pozycji w wierszu zamówienia lub oferty musi być dostarczona w wielu wysyłkach. Każdej wysyłce odpowiada osobny wiersz dostawy. Dwa lub więcej wierszy zamówienia tworzą harmonogram dostawy. Wiersze dostawy mogą mieć różne daty dostawy, ilości, metody dostawy i wymiary magazynowania, takie jak oddział i magazyn.  

**Przykład harmonogramu dostaw**

| Pozycja                              | Wartość                                    |
|-----------------------------------|------------------------------------------|
| Suma zamówienia (wiersz oryginalnego zamówienia) | 600 krzeseł                               |
| Wymagany harmonogram dostaw       | 100 krzeseł na miesiąc                     |
| Żądany przedział czasowy dostaw | 6 miesięcy, w pierwszym dniu każdego miesiąca |

W tym scenariuszu klient żąda dostawy 600 krzeseł w partiach po 100 sztuk w okresie 6 miesięcy. Aby śledzić wymagania dostawy, można utworzyć harmonogram dostaw. Na stronie harmonogram dostaw można utworzyć sześć osobnych wierszy dostawy. Każdy wiersz dostawy zawiera 100 krzeseł i wskazuje datę ich dostarczenia do odbiorcy. W tym przypadku każdy wiersz jest przesunięty na pierwsze dni kolejnych sześciu miesięcy.  

Tworząc harmonogram dostaw, typ wiersza oryginalnego zamówienia jest automatycznie zmieniany na **Wiersz zamówienia z wieloma dostawami**. Wiersz tego typu jest określany jako wiersz handlowy i jest oznaczony ikoną. Wiersz dostawy jest oznaczony inną ikoną. Jeśli zmienisz ilość w wierszu dostawy, wiersz handlowy zostanie zaktualizowany do łącznej ilości harmonogramu dostawy. Jeśli w umowie handlowej zdefiniowano łączny rabat na zamówienie, harmonogram dostaw zapewnia, że zamówienie będzie kwalifikowało się do otrzymania rabatu końcowego, nawet jeśli zostanie podzielone na osobne dostawy.  

Zamówienia z harmonogramem dostaw są przetwarzane na podstawie wierszy dostawy. Przetwarzanie obejmuje księgowanie dokumentów dostawy, dokumentów przyjęcia produktów, i fakturowanie.  

Wydruki dokumentów zamówień i ofert z harmonogramem dostaw zawierają tylko wiersze dostaw. Nie zawierają oryginalnych wierszy (handlowych). **Uwaga:** w przypadku wykonania czynności opisanych poniżej będą widoczne tylko wiersze dostawy.

-   Księgowanie
-   Kopiowanie stron
-   Przeglądanie stron listy i raportów

W przypadku potwierdzenia oferty sprzedaży wyświetlane zamówienia sprzedaży będą zawierały cały harmonogram dostaw, łącznie z wierszami zamówienia, dla których określono wiele dostaw. Ponadto cały harmonogram dostaw jest widoczny na wszystkich głównych stronach, takich jak zamówienia sprzedaży, oferty sprzedaży i zamówienia zakupu.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]