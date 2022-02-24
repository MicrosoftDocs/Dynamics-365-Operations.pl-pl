---
title: Środki trwałe i zlecenia pracy
description: W tym temacie opisano zlecenia pracy i środki trwałe w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4eadbdc452a5b7d28adfa0f102a9a727faad3c07
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016710"
---
# <a name="work-orders-and-fixed-assets"></a>Środki trwałe i zlecenia pracy

[!include [banner](../../includes/banner.md)]


W module Zarządzanie składnikami majątku, składniki majątku mogą być powiązane ze środkami trwałymi oraz można tworzyć zlecenia pracy dla tych składników. W przypadku korzystania z tej funkcji można zapoznać się z ogólnym przeglądem środków trwałych, powiązanych projektów inwestycyjnych oraz kosztami zarejestrowanymi w projektach inwestycyjnych w modułach **Zarządzanie projektami i ich księgowanie** oraz **Środki trwałe** w Microsoft Dynamics 365 for Finance and Operations.

>[!NOTE]
>Pole **Numer środka trwałego** jest wypełniane tylko w projekcie zadania zlecenia pracy, jeśli w projekcie zadania zlecenia pracy jako typ projektu wybrano typ **Inwestycja**.

Poniższa ilustracja przedstawia relację między projektem inwestycyjnym w module **zarządzanie projektami i ich księgowanie** oraz projektem zadania zlecenia pracy.

![Rysunek 1](media/24-work-orders.png)

Poniższa procedura opisuje relację między składnikami majątku, zleceniami pracy, projektami zadań zlecenia pracy i środkami trwałymi.

1. Tworzony jest składnik majątku powiązany z środkiem trwałym.

![Rysunek 2](media/25-work-orders.png)

2. Podczas konfigurowania typów zleceń pracy na stronie **Typy zleceń pracy** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Typy zleceń pracy**) tworzony jest typ zlecenia pracy służący do obsługi inwestycji. Zobacz również [Typy zleceń pracy](../setup-for-work-orders/work-order-types.md).

![Rysunek 3](media/26-work-orders.png)

3. Podczas konfigurowania grup projektów zleceń pracy na karcie **Grupa projektów** na stronie **Ustawienia projektu zlecenia pracy** (**Zarządzanie składnikami majątku** > **Konfiguracja** > **Zlecenia pracy** > **Ustawienia projektu**), tworzy relację między typem zlecenia pracy używanym w inwestycjach a grupą projektów utworzoną dla inwestycji na stronie **Grupy projektów** w module **Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** > **Konfiguracja** > **Księgowanie** > **Grupy projektów**).

![Rysunek 4](media/27-work-orders.png)

4. Podczas tworzenia zlecenia pracy związanego ze środkiem trwałym należy wybrać typ zlecenia pracy używanego do obsługi inwestycji, na przykład **Inwestycja**.

5. Po utworzeniu zlecenia pracy typ powiązanego zlecenia jest pokazywany na stronie **Wszystkie zlecenia pracy**.

![Rysunek 5](media/28-work-orders.png)

6. Po utworzeniu zlecenia produkcyjnego projekt powiązany z danym zleceniem produkcyjnym jest tworzony na stronie **Wszystkie projekty** w module **Zarządzanie projektami i ich księgowanie** (**Zarządzanie projektami i ich księgowanie** > **Projekty** > **Wszystkie projekty**). Aby wyświetlić informacje związane z projektem, należy wybrać łącze w polu **Identyfikator projektu** na karcie **Ogólne** w skróconej karcie **Szczegóły wiersza** na stronie **Wszystkie zlecenia pracy** w module **Zarządzanie składnikami majątku** (**Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy**).

![Rysunek 6](media/29-work-orders.png)

7. Aby wyświetlić przegląd projektów skojarzonych z środkiem trwałym, należy wybrać **Środki trwałe** > **Środki trwałe** > **Środki trwałe**, a następnie w polu **Numer środka trwałego** wybrać łącze dla środka trwałego w celu otwarcia widoku szczegółów. Rozwiń **Pokrewne okienko informacji** po prawej stronie strony i wybierz skróconą kartę **Skojarzone projekty**.

