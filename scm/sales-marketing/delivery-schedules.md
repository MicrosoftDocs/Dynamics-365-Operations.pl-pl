---
title: Harmonogramy dostaw
description: "Harmonogramy dostaw umożliwiają śledzenie ilości w wierszu zamówienia, gdy jest używanych wiele dostaw dla jednego zamówienia sprzedaży, oferty sprzedaży lub zamówienia zakupu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: fbada697060c823b0afdb72d1c0cfd8703f4d527
ms.lasthandoff: 03/31/2017


---

# <a name="delivery-schedules"></a>Harmonogramy dostaw

[!include[banner](../includes/banner.md)]


Harmonogramy dostaw umożliwiają śledzenie ilości w wierszu zamówienia, gdy jest używanych wiele dostaw dla jednego zamówienia sprzedaży, oferty sprzedaży lub zamówienia zakupu.

Harmonogramu dostaw używa się, gdy łączna ilość pozycji w wierszu zamówienia lub oferty musi być dostarczona w wielu wysyłkach. Każdej wysyłce odpowiada osobny wiersz dostawy. Dwa lub więcej wierszy zamówienia tworzą harmonogram dostawy. Wiersze dostawy mogą mieć różne daty dostawy, ilości, metody dostawy i wymiary magazynowania, takie jak oddział i magazyn.  

**Przykład harmonogramu dostaw**

|                                   |                                          |
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




